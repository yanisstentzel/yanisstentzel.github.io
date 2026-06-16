---
title: "Running Dashboard"
description: "Automated tracking of my workouts and performance."
layout: "single"
---

{{< rawhtml >}}
<!-- Inclusion de Chart.js pour la Data Viz -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<style>
/* Style intégré pour s'adapter au mode sombre de PaperMod */
.dashboard-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 20px;
}
.metrics-row {
    display: flex;
    justify-content: space-between;
    gap: 15px;
    flex-wrap: wrap;
}
.metric-card {
    background-color: var(--entry);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    flex: 1;
    min-width: 120px;
    text-align: center;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
}
.metric-card h3 {
    margin: 0;
    font-size: 0.9rem;
    color: var(--secondary);
    font-weight: normal;
}
.metric-card p {
    margin: 10px 0 0 0;
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary);
}
.chart-container {
    background-color: var(--entry);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    position: relative;
    height: 300px;
    width: 100%;
}
</style>

<div class="dashboard-container">
    <!-- Cartes des records (Données statiques pour la maquette) -->
    <div class="metrics-row">
        <div class="metric-card">
            <h3>Record 5K</h3>
            <p>24:38</p>
        </div>
        <div class="metric-card">
            <h3>Record 10K</h3>
            <p>58:06</p>
        </div>
        <div class="metric-card">
            <h3>Semi-Marathon</h3>
            <p>2:09:00</p>
        </div>
    </div>

    <!-- Graphique d'évolution -->
    <div class="chart-container">
        <canvas id="paceChart"></canvas>
    </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    const ctx = document.getElementById('paceChart').getContext('2d');
    
    // Configuration du thème pour Chart.js en fonction de PaperMod
    Chart.defaults.color = '#a9a9b3';
    Chart.defaults.borderColor = 'rgba(255, 255, 255, 0.1)';

    const paceChart = new Chart(ctx, {
        type: 'line',
        data: {
            // Courbe de progression démarrant à la mi-avril
            labels: ['Mi-Avril', 'Fin Avril', 'Début Mai', 'Mi-Mai', 'Fin Mai', 'Juin'],
            datasets: [{
                label: 'Allure moyenne (min/km)',
                data: [6.15, 6.05, 5.95, 5.85, 5.80, 5.75],
                borderColor: '#4a90e2',
                backgroundColor: 'rgba(74, 144, 226, 0.1)',
                borderWidth: 3,
                pointBackgroundColor: '#4a90e2',
                pointRadius: 4,
                fill: true,
                tension: 0.3 // Courbe arrondie
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    display: false
                },
                tooltip: {
                    callbacks: {
                        label: function(context) {
                            return context.raw + ' min/km';
                        }
                    }
                }
            },
            scales: {
                y: {
                    reverse: true, // Inverser l'axe Y (plus le chiffre est bas, plus on est rapide)
                    title: {
                        display: true,
                        text: 'Allure (min/km)'
                    }
                }
            }
        }
    });
});
</script>
{{< /rawhtml >}}