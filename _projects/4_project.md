---
layout: page
title: "Coding Stuff"
description: "Coding tools and fun gimmicks"
img: /assets/img/prof_pic.jpg
importance: 2
category: Fun
published: true
---

<div class="alert alert-info" role="alert">
  <h4 class="alert-heading">🎮 Welcome to the Playground!</h4>
  <p>Ready to explore the exciting world of software development? Let's dive into some code adventures!</p>
</div>

## 🚀 Quick Code Challenge

**Can you spot the bug in this Python function?**

```python
def fibonacci_buggy(n):
    if n <= 1:
        return n
    return fibonacci_buggy(n-1) + fibonacci_buggy(n-2)

# Test it out!
print(fibonacci_buggy(10))  # What's the output?
```

*Hint: This recursive implementation works, but it's not very efficient! Can you think of a better way?*

## 🧪 Vapor Pressure Estimator Tool

**Estimate the vapor pressure of ALD precursors using molecular structure analysis!**

<div class="vapor-pressure-tool">
    <div class="card">
        <div class="card-header">
            <h5>🔬 ALD Precursor Vapor Pressure Calculator</h5>
        </div>
        <div class="card-body">
            <form id="vp-form">
                <div class="mb-3">
                    <label for="precursor-input" class="form-label">Enter ALD Precursor (SMILES or Chemical Name)</label>
                    <input type="text" class="form-control" id="precursor-input" placeholder="e.g., CC[Al](CC)CC or TMA" required>
                    <div class="form-text">Examples: TMA (C[Al](C)C), TEMAZ (N[N](C)C), Cu(hfac)2, etc.</div>
                </div>
                <div class="mb-3">
                    <label for="temperature-input" class="form-label">Temperature (°C)</label>
                    <input type="number" class="form-control" id="temperature-input" value="25" min="-50" max="200">
                </div>
                <button type="submit" class="btn btn-primary" id="calculate-btn">
                    <span class="spinner-border spinner-border-sm d-none" role="status"></span>
                    Calculate Vapor Pressure
                </button>
            </form>
            
            <div id="results" class="mt-4 d-none">
                <h6>Results:</h6>
                <div class="alert alert-success" id="vp-result"></div>
                <div class="row">
                    <div class="col-md-6">
                        <div class="card bg-light">
                            <div class="card-body">
                                <h6>Molecular Properties</h6>
                                <p id="mol-properties">Loading...</p>
                            </div>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="card bg-light">
                            <div class="card-body">
                                <h6>Estimation Method</h6>
                                <p id="estimation-method">Group contribution method based on molecular structure</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div id="error" class="mt-3 d-none">
                <div class="alert alert-danger" id="error-message"></div>
            </div>
        </div>
    </div>
</div>

<script src="https://unpkg.com/@rdkit/rdkit@2023.3.1/Code/MinimalLib/dist/RDKit_minimal.js"></script>
<script>
document.addEventListener('DOMContentLoaded', function() {
    let rdkitModule;
    
    // Initialize RDKit
    initRDKitModule().then(function(RDKit) {
        rdkitModule = RDKit;
        console.log('RDKit initialized');
    }).catch(function(error) {
        console.error('Failed to initialize RDKit:', error);
        showError('Failed to load cheminformatics library. Please refresh the page.');
    });
    
    // Form submission
    document.getElementById('vp-form').addEventListener('submit', function(e) {
        e.preventDefault();
        calculateVaporPressure();
    });
    
    async function calculateVaporPressure() {
        const input = document.getElementById('precursor-input').value.trim();
        const temperature = parseFloat(document.getElementById('temperature-input').value);
        
        if (!input) {
            showError('Please enter a precursor SMILES or name');
            return;
        }
        
        if (!rdkitModule) {
            showError('Cheminformatics library not loaded. Please refresh the page.');
            return;
        }
        
        showLoading(true);
        hideError();
        
        try {
            // Try to parse as SMILES first
            let mol = rdkitModule.get_mol(input);
            
            if (!mol) {
                // If SMILES fails, try common ALD precursor lookup
                mol = getCommonPrecursorMol(input, rdkitModule);
                if (!mol) {
                    throw new Error('Could not parse molecule. Please enter a valid SMILES string or select from common precursors.');
                }
            }
            
            // Calculate molecular properties
            const mw = mol.get_mol_wt();
            const formula = mol.get_molecular_formula();
            const numAtoms = mol.get_num_atoms();
            const numHeavyAtoms = mol.get_num_heavy_atoms();
            
            // Simple group contribution vapor pressure estimation
            const vpEstimate = estimateVaporPressure(mol, temperature);
            
            // Display results
            document.getElementById('vp-result').innerHTML = `
                <strong>Estimated Vapor Pressure:</strong> ${vpEstimate.pressure.toExponential(2)} Torr<br>
                <strong>Temperature:</strong> ${temperature}°C<br>
                <strong>Confidence:</strong> ${vpEstimate.confidence}<br>
                <small>This is a rough estimate using group contribution methods. Actual values may vary significantly.</small>
            `;
            
            document.getElementById('mol-properties').innerHTML = `
                <strong>Molecular Formula:</strong> ${formula}<br>
                <strong>Molecular Weight:</strong> ${mw.toFixed(2)} g/mol<br>
                <strong>Total Atoms:</strong> ${numAtoms}<br>
                <strong>Heavy Atoms:</strong> ${numHeavyAtoms}
            `;
            
            document.getElementById('results').classList.remove('d-none');
            
        } catch (error) {
            showError(error.message);
        } finally {
            showLoading(false);
        }
    }
    
    function estimateVaporPressure(mol, temperature) {
        // Simple group contribution method for vapor pressure estimation
        // This is a very basic implementation - real vapor pressure prediction is complex
        
        const mw = mol.get_mol_wt();
        const numAtoms = mol.get_num_atoms();
        
        // Count functional groups (simplified)
        let functionalGroups = 0;
        const smiles = mol.get_smiles();
        
        // Count common functional groups
        functionalGroups += (smiles.match(/\[Al\]/g) || []).length; // Aluminum
        functionalGroups += (smiles.match(/\[Cu\]/g) || []).length; // Copper
        functionalGroups += (smiles.match(/\[Zn\]/g) || []).length; // Zinc
        functionalGroups += (smiles.match(/\[Ti\]/g) || []).length; // Titanium
        functionalGroups += (smiles.match(/N/g) || []).length; // Nitrogen
        functionalGroups += (smiles.match(/O/g) || []).length; // Oxygen
        functionalGroups += (smiles.match(/C/g) || []).length * 0.1; // Carbon (weighted less)
        
        // Very rough estimation using modified Clausius-Clapeyron type equation
        // log(P) = A - B/T, where T is in Kelvin
        const T = temperature + 273.15; // Convert to Kelvin
        
        // Base vapor pressure estimation (very approximate)
        let logP = 10 - (3000 / T) - (functionalGroups * 0.5);
        
        // Adjust for molecular weight
        logP -= Math.log10(mw) * 0.3;
        
        const pressure = Math.pow(10, logP);
        
        // Determine confidence based on complexity
        let confidence = "Low";
        if (functionalGroups < 5) confidence = "Medium";
        if (functionalGroups < 3) confidence = "High";
        
        return {
            pressure: pressure,
            confidence: confidence
        };
    }
    
    function getCommonPrecursorMol(name, RDKit) {
        // Common ALD precursors lookup
        const commonPrecursors = {
            'tma': 'C[Al](C)C',
            'temaz': 'CN(C)N(C)C',
            'tdmaz': 'CN(C)N(C)C', // Simplified
            'deaz': 'CCN(CC)N(CC)CC',
            'cuhfac2': 'C7H2CuF6O4', // Simplified SMILES
            'cuthd': 'C11H14CuO4', // Simplified
            'znme2': 'C[Zn]C',
            'znet2': 'CC[Zn]CC',
            'titanium_isopropoxide': 'CC(C)O[Ti](OC(C)C)(OC(C)C)OC(C)C',
            'hafnium_tetrachloride': 'Cl[Hf](Cl)(Cl)Cl'
        };
        
        const smiles = commonPrecursors[name.toLowerCase().replace(/\s+/g, '')];
        if (smiles) {
            return RDKit.get_mol(smiles);
        }
        return null;
    }
    
    function showLoading(show) {
        const spinner = document.querySelector('#calculate-btn .spinner-border');
        const btn = document.getElementById('calculate-btn');
        
        if (show) {
            spinner.classList.remove('d-none');
            btn.disabled = true;
        } else {
            spinner.classList.add('d-none');
            btn.disabled = false;
        }
    }
    
    function showError(message) {
        document.getElementById('error-message').textContent = message;
        document.getElementById('error').classList.remove('d-none');
        document.getElementById('results').classList.add('d-none');
    }
    
    function hideError() {
        document.getElementById('error').classList.add('d-none');
    }
    
    async function initRDKitModule() {
        return new Promise((resolve, reject) => {
            window.RDKit = {
                onRuntimeInitialized: function() {
                    resolve(window.RDKit);
                }
            };
            
            // Load RDKit script if not already loaded
            if (!document.querySelector('script[src*="RDKit"]')) {
                const script = document.createElement('script');
                script.src = 'https://unpkg.com/@rdkit/rdkit@2023.3.1/Code/MinimalLib/dist/RDKit_minimal.js';
                script.onload = function() {
                    // Wait for RDKit to initialize
                    setTimeout(() => {
                        if (window.RDKit && window.RDKit.Module) {
                            resolve(window.RDKit);
                        } else {
                            reject(new Error('RDKit failed to initialize'));
                        }
                    }, 1000);
                };
                script.onerror = reject;
                document.head.appendChild(script);
            }
        });
    }
});
</script>

<style>
.vapor-pressure-tool .card {
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border: none;
}

.vapor-pressure-tool .form-control:focus {
    border-color: var(--global-theme-color);
    box-shadow: 0 0 0 0.2rem rgba(var(--global-theme-color-rgb), 0.25);
}

.vapor-pressure-tool .btn-primary {
    background-color: var(--global-theme-color);
    border-color: var(--global-theme-color);
}

.vapor-pressure-tool .btn-primary:hover {
    background-color: var(--global-theme-color);
    border-color: var(--global-theme-color);
    opacity: 0.9;
}
</style>

## 🎯 Featured Projects Showcase

### 🌐 Web Development Adventures

<div class="row">
    <div class="col-md-6">
        <div class="card h-100 border-primary">
            <div class="card-body">
                <h5 class="card-title">🚀 Full-Stack Fantasy</h5>
                <p class="card-text">Built scalable web applications that handle thousands of users. From React frontends to Node.js backends, I create digital experiences that people love to use.</p>
                <div class="tech-stack">
                    <span class="badge badge-primary">React</span>
                    <span class="badge badge-success">Node.js</span>
                    <span class="badge badge-info">PostgreSQL</span>
                    <span class="badge badge-warning">Docker</span>
                </div>
            </div>
        </div>
    </div>
    <div class="col-md-6">
        <div class="card h-100 border-success">
            <div class="card-body">
                <h5 class="card-title">🤖 AI & Machine Learning Quests</h5>
                <p class="card-text">Trained models that predict the future (well, sort of). From recommendation systems to computer vision, I turn data into intelligent decisions.</p>
                <div class="tech-stack">
                    <span class="badge badge-danger">TensorFlow</span>
                    <span class="badge badge-primary">Python</span>
                    <span class="badge badge-dark">PyTorch</span>
                    <span class="badge badge-info">Scikit-learn</span>
                </div>
            </div>
        </div>
    </div>
</div>

### ☁️ Cloud Architecture Challenges

<div class="row mt-3">
    <div class="col-md-6">
        <div class="card h-100 border-warning">
            <div class="card-body">
                <h5 class="card-title">🏗️ Infrastructure as Code</h5>
                <p class="card-text">Automated the deployment of complex systems using Infrastructure as Code. Because who wants to manually configure servers?</p>
                <div class="tech-stack">
                    <span class="badge badge-secondary">Terraform</span>
                    <span class="badge badge-primary">AWS</span>
                    <span class="badge badge-success">Kubernetes</span>
                    <span class="badge badge-info">Docker</span>
                </div>
            </div>
        </div>
    </div>
    <div class="col-md-6">
        <div class="card h-100 border-danger">
            <div class="card-body">
                <h5 class="card-title">🔒 Security First Development</h5>
                <p class="card-text">Built secure applications that protect user data while maintaining usability. Security isn't just a feature—it's the foundation.</p>
                <div class="tech-stack">
                    <span class="badge badge-dark">OAuth 2.0</span>
                    <span class="badge badge-danger">JWT</span>
                    <span class="badge badge-warning">SSL/TLS</span>
                    <span class="badge badge-info">Encryption</span>
                </div>
            </div>
        </div>
    </div>
</div>

## 🎪 Fun Tech Facts & Trivia

<div class="row">
    <div class="col-md-4">
        <div class="fun-fact">
            <h6>🐛 Bug Origins</h6>
            <p>The term "bug" in programming comes from 1947 when Grace Hopper found an actual bug (moth) in a computer!</p>
        </div>
    </div>
    <div class="col-md-4">
        <div class="fun-fact">
            <h6>⚡ Speed Demon</h6>
            <p>The first computer mouse was made of wood and had just one button. Talk about minimalist design!</p>
        </div>
    </div>
    <div class="col-md-4">
        <div class="fun-fact">
            <h6>🎯 Code Efficiency</h6>
            <p>Good code is like a good joke—timing matters! Efficient algorithms can make the difference between seconds and hours.</p>
        </div>
    </div>
</div>

## 🛠️ Developer Toolbox

**Languages I Speak:**
- 🐍 **Python** - My go-to for everything from data science to web apps
- ☕ **JavaScript/TypeScript** - Making the web interactive and type-safe
- 🏗️ **Java** - Enterprise-grade applications that scale
- ⚡ **C/C++** - When performance is critical
- 🗄️ **SQL** - Talking to databases like a pro

**Tools in My Arsenal:**
- 🐙 **Git** - Version control wizardry
- 🐳 **Docker** - Container magic
- ☁️ **AWS/GCP/Azure** - Cloud computing platforms
- 🧪 **Jest/PyTest** - Testing frameworks
- 📊 **Jupyter** - Interactive data exploration

## 🎖️ Achievement Unlocked!

<div class="achievements">
    <div class="achievement">
        <span class="achievement-icon">🏆</span>
        <strong>Scalability Master</strong> - Built systems serving 10K+ users
    </div>
    <div class="achievement">
        <span class="achievement-icon">🚀</span>
        <strong>Performance Optimizer</strong> - 300% throughput improvement
    </div>
    <div class="achievement">
        <span class="achievement-icon">🎯</span>
        <strong>ML Expert</strong> - 95%+ accuracy on complex models
    </div>
    <div class="achievement">
        <span class="achievement-icon">🌟</span>
        <strong>Open Source Contributor</strong> - 1000+ GitHub stars
    </div>
    <div class="achievement">
        <span class="achievement-icon">👥</span>
        <strong>Team Leader</strong> - Led cross-functional development teams
    </div>
</div>

## 🔗 Explore More Adventures

Ready to see the code in action? Check out my [GitHub profile](https://github.com/atillavarga) for:

- 📁 **Open-source projects** with real-world impact
- 💻 **Code samples** showcasing best practices
- 📚 **Technical tutorials** and documentation
- 🤝 **Collaborations** on exciting software projects

## 🎨 My Development Philosophy

> "Code is poetry in motion. Every function tells a story, every algorithm solves a puzzle, and every deployment brings joy to users."

I believe in:
- **🎯 Problem-First Thinking** - Start with the user's needs, not the technology
- **🧪 Test-Driven Development** - Write tests before code to ensure reliability
- **🔄 Continuous Learning** - Technology evolves, and so do I
- **🤝 Collaborative Coding** - Great software is built by great teams
- **⚡ Performance Matters** - Fast, efficient code creates happy users

---

<div class="text-center mt-4">
    <p class="lead">Thanks for exploring my developer's playground! 🚀</p>
    <p>Have a question or want to collaborate? <a href="mailto:contact@example.com">Let's chat!</a></p>
</div>

