<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestion des Incidents - Présentation</title>
    <style>
        * {
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.7;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #2c3e50;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: #ffffff;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
            margin-top: 40px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2, #f093fb, #f5576c);
        }
        
        h1 {
            font-size: 3rem;
            font-weight: 700;
            color: #2c3e50;
            text-align: center;
            margin-bottom: 40px;
            position: relative;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        
        h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2);
            border-radius: 2px;
        }
        
        h2 {
            font-size: 1.8rem;
            font-weight: 600;
            color: #2c3e50;
            margin: 40px 0 20px 0;
            padding: 15px 20px;
            background: linear-gradient(135deg, #f8f9ff 0%, #e8ecff 100%);
            border-left: 5px solid #667eea;
            border-radius: 10px;
            position: relative;
        }
        
        h3 {
            color: #34495e;
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        .group-info {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 40px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }
        
        .group-info h3 {
            color: white;
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        .group-info p {
            font-size: 1.1rem;
            margin: 0;
            font-weight: 500;
        }
        
        .matrix-container, .workflow-container, .funnel-container {
            text-align: center;
            margin: 40px 0;
            background: linear-gradient(135deg, #f8f9ff 0%, #ffffff 100%);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            border: 1px solid #e8ecff;
        }
        
        .priority-matrix {
            display: inline-block;
            border-collapse: separate;
            border-spacing: 2px;
            margin: 20px auto;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .priority-matrix th, .priority-matrix td {
            padding: 18px 24px;
            text-align: center;
            font-weight: 600;
            font-size: 0.95rem;
            border: none;
        }
        
        .priority-matrix th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .p1 { 
            background: linear-gradient(135deg, #ff416c 0%, #ff4757 100%); 
            color: white; 
            box-shadow: 0 4px 15px rgba(255, 65, 108, 0.3);
        }
        .p2 { 
            background: linear-gradient(135deg, #ff9500 0%, #ff6b35 100%); 
            color: white;
            box-shadow: 0 4px 15px rgba(255, 149, 0, 0.3);
        }
        .p3 { 
            background: linear-gradient(135deg, #feca57 0%, #ff9ff3 100%);
            color: #2c3e50;
            box-shadow: 0 4px 15px rgba(254, 202, 87, 0.3);
        }
        .p4 { 
            background: linear-gradient(135deg, #48dbfb 0%, #0abde3 100%); 
            color: white;
            box-shadow: 0 4px 15px rgba(72, 219, 251, 0.3);
        }
        
        .workflow-step {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 50px;
            padding: 20px 30px;
            margin: 15px auto;
            max-width: 500px;
            font-weight: 600;
            font-size: 1rem;
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .workflow-step:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(102, 126, 234, 0.4);
        }
        
        .arrow {
            font-size: 28px;
            color: #667eea;
            margin: 15px 0;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        
        .funnel-level {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 50px;
            padding: 18px 25px;
            margin: 12px auto;
            font-weight: 600;
            position: relative;
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.2);
            transition: all 0.3s ease;
        }
        
        .funnel-level:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(102, 126, 234, 0.3);
        }
        
        .level1 { width: 90%; background: linear-gradient(135deg, #ff6b6b 0%, #ee5a24 100%); }
        .level2 { width: 85%; background: linear-gradient(135deg, #ff9500 0%, #ff6348 100%); }
        .level3 { width: 80%; background: linear-gradient(135deg, #feca57 0%, #ff9ff3 100%); }
        .level4 { width: 75%; background: linear-gradient(135deg, #48dbfb 0%, #0abde3 100%); }
        .level5 { width: 70%; background: linear-gradient(135deg, #1dd1a1 0%, #10ac84 100%); }
        .level6 { width: 65%; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .level7 { width: 60%; background: linear-gradient(135deg, #764ba2 0%, #667eea 100%); }
        .level8 { width: 55%; background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%); }
        .level9 { width: 50%; background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%); }
        
        ul {
            background: linear-gradient(135deg, #f8f9ff 0%, #ffffff 100%);
            padding: 25px 30px;
            border-radius: 15px;
            border-left: 5px solid #667eea;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }
        
        li {
            margin-bottom: 12px;
            font-size: 1.05rem;
            color: #34495e;
            position: relative;
            padding-left: 20px;
        }
        
        li::before {
            content: '•';
            color: #667eea;
            font-size: 1.2rem;
            position: absolute;
            left: 0;
            top: 0;
        }
        
        .highlight {
            background: linear-gradient(135deg, #fff9e6 0%, #fff3cd 100%);
            padding: 25px;
            border-left: 5px solid #f39c12;
            border-radius: 10px;
            margin: 30px 0;
            box-shadow: 0 5px 20px rgba(243, 156, 18, 0.1);
        }
        
        .example-box {
            background: linear-gradient(135deg, #e8f4ff 0%, #d1ecf1 100%);
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            border-left: 5px solid #3498db;
            box-shadow: 0 5px 20px rgba(52, 152, 219, 0.1);
            transition: all 0.3s ease;
        }
        
        .example-box:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(52, 152, 219, 0.15);
        }
        
        .example-box h3 {
            color: #2980b9;
            margin-bottom: 15px;
            font-size: 1.2rem;
        }
        
        p {
            font-size: 1.05rem;
            color: #34495e;
            line-height: 1.7;
            margin-bottom: 15px;
        }
        
        strong {
            color: #2c3e50;
            font-weight: 600;
        }
        
        ol {
            counter-reset: item;
            padding-left: 0;
        }
        
        ol li {
            counter-increment: item;
            margin-bottom: 15px;
            padding-left: 40px;
            position: relative;
        }
        
        ol li::before {
            content: counter(item);
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 50%;
            width: 25px;
            height: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            left: 0;
            top: 2px;
            font-weight: 600;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .container {
                margin: 20px;
                padding: 25px;
                border-radius: 15px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            h2 {
                font-size: 1.5rem;
                padding: 12px 15px;
            }
            
            .priority-matrix th, .priority-matrix td {
                padding: 12px 16px;
                font-size: 0.85rem;
            }
            
            .workflow-step {
                padding: 15px 20px;
                font-size: 0.9rem;
                max-width: 90%;
            }
            
            .matrix-container, .workflow-container, .funnel-container {
                padding: 20px;
                margin: 25px 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>GESTION DES INCIDENTS</h1>
        
        <div class="group-info">
            <h3>GROUPE :</h3>
            <p><strong>Matys Miranville • Jean Edmond • David Dalele • Nathan Begue</strong></p>
        </div>

        <h2>1. Problématique Actuelle</h2>
        <div class="highlight">
            <p><strong>Aujourd'hui :</strong> Aucun outil de suivi → perte de temps, informations dispersées, pas de traçabilité</p>
        </div>
        <p><strong>Conséquences :</strong></p>
        <ul>
            <li>Impossible de mesurer la charge réelle (40 incidents/jour)</li>
            <li>Risque de perte de savoir (incidents non documentés)</li>
            <li>Pas de statistiques fiables pour améliorer le service</li>
            <li>Insatisfaction des utilisateurs → baisse de productivité</li>
        </ul>
        <p><strong>Solution :</strong> Mise en place d'un outil ITSM type GLPI ou WHD (Web Help Desk)</p>

        <h2>2. Critères de l'Outil ITSM</h2>
        <ul>
            <li>Enregistrement automatique et manuel des incidents</li>
            <li>Attribution automatique selon la catégorie/compétence</li>
            <li>Suivi du cycle de vie : création → résolution → clôture</li>
            <li>Gestion des priorités</li>
            <li>Tableaux de bord et reporting</li>
            <li>Base de connaissances intégrée</li>
            <li>Interface simple pour les utilisateurs</li>
            <li>Intégration avec Active Directory</li>
        </ul>

        <h2>3. Matrice Impact × Urgence</h2>
        <div class="matrix-container">
            <table class="priority-matrix">
                <tr>
                    <th></th>
                    <th>Faible</th>
                    <th>Moyen</th>
                    <th>Élevé</th>
                    <th>Critique</th>
                </tr>
                <tr>
                    <th>Critique</th>
                    <td class="p2">P2</td>
                    <td class="p1">P1</td>
                    <td class="p1">P1</td>
                    <td class="p1">P1</td>
                </tr>
                <tr>
                    <th>Élevée</th>
                    <td class="p2">P2</td>
                    <td class="p2">P2</td>
                    <td class="p1">P1</td>
                    <td class="p1">P1</td>
                </tr>
                <tr>
                    <th>Moyenne</th>
                    <td class="p3">P3</td>
                    <td class="p2">P2</td>
                    <td class="p2">P2</td>
                    <td class="p1">P1</td>
                </tr>
                <tr>
                    <th>Faible</th>
                    <td class="p4">P4</td>
                    <td class="p3">P3</td>
                    <td class="p2">P2</td>
                    <td class="p1">P1</td>
                </tr>
            </table>
            <p><em>Axe vertical : Urgence | Axe horizontal : Impact</em></p>
        </div>

        <h2>4. Processus de Traitement (Workflow)</h2>
        <div class="workflow-container">
            <div class="workflow-step">Enregistrement de l'incident</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Catégoriser l'incident</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Prioriser selon l'impact/l'incident</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Affecter au Agent de l'équipe informatique</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Diagnostique Initial</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Escalade si besoins</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Résolution de l'incident</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Validation côté client/utilisateur</div>
            <div class="arrow">↓</div>
            <div class="workflow-step">Clôture & Documentation</div>
        </div>

        <h2>5. Processus en Entonnoir</h2>
        <div class="funnel-container">
            <div class="funnel-level level1">1. Enregistrement de l'incident</div>
            <div class="funnel-level level2">2. Catégorisation</div>
            <div class="funnel-level level3">3. Priorisation</div>
            <div class="funnel-level level4">4. Affectation</div>
            <div class="funnel-level level5">5. Diagnostic initial</div>
            <div class="funnel-level level6">6. Escalade si nécessaire</div>
            <div class="funnel-level level7">7. Résolution</div>
            <div class="funnel-level level8">8. Validation utilisateur</div>
            <div class="funnel-level level9">9. Clôture & Documentation</div>
        </div>

        <h2>6. Exemples de Priorités</h2>
        <div class="example-box">
            <h3>Priorité 1 (Critique)</h3>
            <p>Base de données de paie en panne la veille des salaires</p>
        </div>
        <div class="example-box">
            <h3>Priorité 2 (Haute)</h3>
            <p>Équipe comptabilité bloquée en clôture mensuelle</p>
        </div>
        <div class="example-box">
            <h3>Priorité 3 (Moyenne)</h3>
            <p>Problème mail urgent pour un rapport</p>
        </div>
        <div class="example-box">
            <h3>Priorité 4 (Basse)</h3>
            <p>Demande d'installation logiciel non urgent</p>
        </div>

        <h2>7. Indicateurs de Qualité</h2>
        <ul>
            <li>Nombre d'incidents enregistrés/résolus/en attente</li>
            <li>Temps moyen de réponse</li>
            <li>Temps moyen de résolution</li>
            <li>Pourcentage d'incidents résolus au premier niveau</li>
            <li>Nombre d'incidents résolus dans les délais</li>
            <li>Satisfaction utilisateurs</li>
        </ul>

        <h2>8. Exemple Concret</h2>
        <div class="example-box">
            <h3>Scénario : Utilisateur RH ne peut pas accéder à l'application de paie</h3>
            <ol>
                <li><strong>Enregistrement :</strong> Via portail (catégorie Application RH)</li>
                <li><strong>Catégorisation :</strong> Application métiers / Ressources Humaines</li>
                <li><strong>Priorisation :</strong> Impact fort + Urgence forte → Priorité 1</li>
                <li><strong>Affectation :</strong> Équipe support applicatif RH</li>
                <li><strong>Diagnostic :</strong> Problème de connexion DB</li>
                <li><strong>Escalade :</strong> Vers DBA</li>
                <li><strong>Résolution :</strong> Redémarrage service DB</li>
                <li><strong>Validation :</strong> Avec l'utilisateur</li>
                <li><strong>Clôture :</strong> Documentation dans base de connaissances</li>
            </ol>
        </div>
    </div>
</body>
</html>
