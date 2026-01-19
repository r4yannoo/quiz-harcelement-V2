<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz : Protection contre le harcèlement</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', system-ui, sans-serif;
            line-height: 1.6;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            padding: 30px;
        }

        .header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid #eaeaea;
        }

        .header h1 {
            color: #2c3e50;
            font-size: 28px;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .header p {
            color: #7f8c8d;
            font-size: 16px;
        }

        /* Navigation */
        .navigation {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            margin-bottom: 30px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 12px;
        }

        .nav-btn {
            padding: 10px 20px;
            background: white;
            border: 2px solid #3498db;
            color: #3498db;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 14px;
        }

        .nav-btn:hover {
            background: #3498db;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.2);
        }

        /* Questions */
        .theme {
            display: none;
        }

        .theme.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .question-container {
            margin-bottom: 25px;
            padding: 25px;
            background: #ffffff;
            border-radius: 15px;
            border-left: 5px solid #3498db;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }

        .question-container:hover {
            transform: translateY(-2px);
        }

        .question-number {
            display: inline-block;
            background: #3498db;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: 600;
            margin-bottom: 15px;
            font-size: 14px;
        }

        .question-text {
            font-size: 18px;
            color: #2c3e50;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .options {
            display: grid;
            gap: 12px;
            margin-bottom: 20px;
        }

        .option {
            padding: 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            background: #fafafa;
        }

        .option:hover {
            border-color: #3498db;
            background: #f0f8ff;
        }

        .option input {
            margin-right: 12px;
            transform: scale(1.2);
        }

        .option label {
            cursor: pointer;
            font-size: 16px;
            color: #555;
            flex: 1;
        }

        .validate-btn {
            display: block;
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
            margin-top: 10px;
        }

        .validate-btn:hover {
            background: linear-gradient(135deg, #2980b9, #1f6396);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        /* Feedback */
        .feedback {
            margin-top: 15px;
            padding: 15px;
            border-radius: 10px;
            display: none;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-10px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .feedback.correct {
            background: #d4edda;
            border: 2px solid #27ae60;
            color: #155724;
        }

        .feedback.incorrect {
            background: #f8d7da;
            border: 2px solid #e74c3c;
            color: #721c24;
        }

        /* Score */
        .score-container {
            text-align: center;
            margin: 30px 0;
            padding: 25px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            color: white;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .score-label {
            font-size: 16px;
            opacity: 0.9;
            margin-bottom: 10px;
        }

        .score-value {
            font-size: 48px;
            font-weight: 700;
            color: #2ecc71;
            margin-bottom: 10px;
        }

        .score-total {
            font-size: 18px;
            opacity: 0.8;
        }

        /* Diplôme */
        .diploma-btn {
            display: block;
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #2ecc71, #27ae60);
            color: white;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-size: 18px;
            font-weight: 700;
            transition: all 0.3s ease;
            margin: 30px 0;
            box-shadow: 0 10px 20px rgba(46, 204, 113, 0.2);
        }

        .diploma-btn:hover {
            background: linear-gradient(135deg, #27ae60, #219653);
            transform: translateY(-3px);
            box-shadow: 0 15px 25px rgba(46, 204, 113, 0.3);
        }

        /* Thème actif */
        .theme h2 {
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
            margin-bottom: 25px;
            font-size: 24px;
        }

        /* Barre de progression */
        .progress-container {
            margin-bottom: 25px;
        }

        .progress-bar {
            height: 8px;
            background: #ecf0f1;
            border-radius: 4px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #3498db, #2ecc71);
            width: 0%;
            transition: width 0.5s ease;
        }

        .progress-text {
            display: flex;
            justify-content: space-between;
            margin-top: 8px;
            font-size: 14px;
            color: #7f8c8d;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 20px;
                border-radius: 15px;
            }

            .header h1 {
                font-size: 22px;
            }

            .nav-btn {
                padding: 8px 15px;
                font-size: 13px;
            }

            .question-text {
                font-size: 16px;
            }

            .option label {
                font-size: 15px;
            }

            .score-value {
                font-size: 36px;
            }
        }

        @media (max-width: 480px) {
            body {
                padding: 10px;
            }

            .container {
                padding: 15px;
            }

            .navigation {
                padding: 15px;
            }

            .question-container {
                padding: 20px;
            }

            .validate-btn, .diploma-btn {
                padding: 15px;
                font-size: 16px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📚 Quiz Professionnel</h1>
            <p>Protection des agents victimes de harcèlement dans les collectivités territoriales</p>
        </div>

        <!-- Navigation -->
        <div class="navigation">
            <button class="nav-btn" onclick="showTheme('theme1')">1. Cadre légal</button>
            <button class="nav-btn" onclick="showTheme('theme2')">2. Signalement</button>
            <button class="nav-btn" onclick="showTheme('theme3')">3. Enquête</button>
            <button class="nav-btn" onclick="showTheme('theme4')">4. Protection</button>
            <button class="nav-btn" onclick="showTheme('theme5')">5. Sanctions</button>
            <button class="nav-btn" onclick="showTheme('theme6')">6. Caractérisation</button>
        </div>

        <!-- Barre de progression -->
        <div class="progress-container">
            <div class="progress-bar">
                <div class="progress-fill" id="progress-fill"></div>
            </div>
            <div class="progress-text">
                <span>Progression</span>
                <span id="progress-percent">0%</span>
            </div>
        </div>

        <!-- Thématique 1 : Cadre légal protecteur -->
        <div id="theme1" class="theme active">
            <h2>📖 1. Cadre légal protecteur</h2>
            
            <!-- Question 1 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">La loi du 6 août 2019 de transformation de la fonction publique a introduit une obligation majeure pour les collectivités territoriales. Laquelle ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q1" value="a" id="q1a">
                        <label for="q1a">La création d'un registre public des cas de harcèlement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="b" id="q1b">
                        <label for="q1b">La désignation obligatoire d'un référent harcèlement dans chaque collectivité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="c" id="q1c">
                        <label for="q1c">L'obligation de licencier tout agent condamné pour harcèlement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="d" id="q1d">
                        <label for="q1d">La suppression des comités d'hygiène et de sécurité</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q1', 'b', 'La loi du 6 août 2019 a rendu obligatoire la désignation d\'un référent harcèlement dans chaque collectivité territoriale, conformément à l\'article L. 135 du Code général de la fonction publique. Ce référent a pour mission d\'accueillir, informer et orienter les agents victimes ou témoins de harcèlement.')">✓ Valider cette réponse</button>
                <div id="feedback1" class="feedback"></div>
            </div>
            
            <!-- Question 2 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Quel article du Code général de la fonction publique impose aux employeurs publics de garantir des conditions de travail préservant la santé physique et mentale des agents, incluant la prévention du harcèlement ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q2" value="a" id="q2a">
                        <label for="q2a">Article L. 134-1</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="b" id="q2b">
                        <label for="q2b">Article L. 135</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="c" id="q2c">
                        <label for="q2c">Article L. 136-1</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="d" id="q2d">
                        <label for="q2d">Article L. 133-3</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q2', 'c', 'L\'article L. 136-1 du Code général de la fonction publique impose aux employeurs publics de prendre les dispositions nécessaires pour garantir des conditions de travail préservant la santé physique et mentale des agents. Cela inclut explicitement la prévention et la lutte contre toutes les formes de harcèlement et de violences sexistes et sexuelles.')">✓ Valider cette réponse</button>
                <div id="feedback2" class="feedback"></div>
            </div>
            
            <!-- Question 3 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Depuis la loi du 6 août 2019, quelle obligation supplémentaire pèse sur les employeurs publics en matière de santé mentale des agents, au-delà de la simple prévention des risques professionnels classiques ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q3" value="a" id="q3a">
                        <label for="q3a">La mise en place d'un suivi psychologique obligatoire pour tous les agents</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q3" value="b" id="q3b">
                        <label for="q3b">La création d'une cellule de crise dédiée aux risques psychosociaux</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q3" value="c" id="q3c">
                        <label for="q3c">Une obligation générale de sécurité étendue à la protection de la santé mentale, incluant la prévention du harcèlement moral et sexuel</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q3" value="d" id="q3d">
                        <label for="q3d">L'obligation de former tous les agents aux techniques de méditation et de gestion du stress</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q3', 'c', 'La loi du 6 août 2019 a étendu l\'obligation générale de sécurité des employeurs publics pour inclure explicitement la protection de la santé mentale des agents. Cela signifie que les collectivités doivent désormais mettre en place des mesures concrètes pour prévenir le harcèlement moral et sexuel, ainsi que les violences sexistes, en plus des risques physiques traditionnels.')">✓ Valider cette réponse</button>
                <div id="feedback3" class="feedback"></div>
            </div>
            
            <!-- Question 4 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">Quel texte a renforcé les obligations des employeurs publics en matière de prévention du harcèlement, en imposant notamment la désignation d'un référent et en créant une obligation d'enquête administrative ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q4" value="a" id="q4a">
                        <label for="q4a">Le décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="b" id="q4b">
                        <label for="q4b">La Charte de la DGAFP de novembre 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="c" id="q4c">
                        <label for="q4c">La loi du 6 août 2019 de transformation de la fonction publique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="d" id="q4d">
                        <label for="q4d">L'accord relatif à l'égalité professionnelle du 30 novembre 2018</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q4', 'c', 'La loi du 6 août 2019 a marqué un tournant en renforçant significativement les obligations des employeurs publics. Elle a notamment imposé la désignation obligatoire d\'un référent harcèlement dans chaque collectivité, ainsi qu\'une obligation d\'enquête administrative dès qu\'un agent signale des faits de harcèlement. Ces mesures visent à garantir une réponse rapide et efficace pour protéger les victimes.')">✓ Valider cette réponse</button>
                <div id="feedback4" class="feedback"></div>
            </div>
            
            <!-- Question 5 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Quelle instance a publié en novembre 2019 une Charte visant à encadrer le fonctionnement des dispositifs de signalement et de traitement des situations de harcèlement dans la fonction publique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q5" value="a" id="q5a">
                        <label for="q5a">Le Défenseur des droits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q5" value="b" id="q5b">
                        <label for="q5b">La Direction générale de l'administration et de la fonction publique (DGAFP)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q5" value="c" id="q5c">
                        <label for="q5c">Le Conseil d'État</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q5" value="d" id="q5d">
                        <label for="q5d">Le Comité Social Territorial</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q5', 'b', 'La Direction générale de l\'administration et de la fonction publique (DGAFP) a publié en novembre 2019 une Charte de fonctionnement des dispositifs de signalement et de traitement des situations de violences sexuelles, de discrimination, de harcèlement sexuel ou moral, et d\'agissements sexistes. Cette Charte constitue un référentiel essentiel pour les employeurs publics.')">✓ Valider cette réponse</button>
                <div id="feedback5" class="feedback"></div>
            </div>
            
            <!-- Question 6 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">Quel accord signé en 2018 a inspiré la Charte de la DGAFP sur la prévention du harcèlement et des violences sexistes et sexuelles dans la fonction publique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q6" value="a" id="q6a">
                        <label for="q6a">L'accord relatif à l'égalité professionnelle entre les femmes et les hommes dans la fonction publique, signé le 30 novembre 2018</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="b" id="q6b">
                        <label for="q6b">La loi Sapin II du 9 décembre 2016</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="c" id="q6c">
                        <label for="q6c">Le décret du 13 mars 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="d" id="q6d">
                        <label for="q6d">La convention collective nationale de la fonction publique territoriale</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q6', 'a', 'La Charte de la DGAFP s\'inscrit dans la continuité de l\'accord relatif à l\'égalité professionnelle entre les femmes et les hommes dans la fonction publique, signé le 30 novembre 2018. Cet accord engage les employeurs publics à mettre en œuvre des actions concrètes pour prévenir et lutter contre les violences sexistes et sexuelles, ainsi que le harcèlement moral et sexuel.')">✓ Valider cette réponse</button>
                <div id="feedback6" class="feedback"></div>
            </div>
            
            <!-- Question 7 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Quel décret, entré en vigueur le 1er février 2025, a modernisé le système de signalement des actes de harcèlement dans les collectivités territoriales, en renforçant notamment les exigences de confidentialité et les délais de traitement ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q7" value="a" id="q7a">
                        <label for="q7a">Le décret du 13 mars 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="b" id="q7b">
                        <label for="q7b">Le décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="c" id="q7c">
                        <label for="q7c">Le décret du 28 mai 1982</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="d" id="q7d">
                        <label for="q7d">Le décret du 4 novembre 1992</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q7', 'b', 'Le décret du 6 novembre 2024, entré en vigueur le 1er février 2025, a profondément modernisé le système de signalement des actes de harcèlement. Il a renforcé les exigences de confidentialité, précisé les procédures de traitement avec des délais contraignants, et permis la mutualisation des dispositifs entre collectivités ou via les centres de gestion.')">✓ Valider cette réponse</button>
                <div id="feedback7" class="feedback"></div>
            </div>
            
            <!-- Question 8 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Quelle obligation générale pèse sur les employeurs publics en matière de santé mentale des agents, selon l'article L. 136-1 du Code général de la fonction publique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q8" value="a" id="q8a">
                        <label for="q8a">Une obligation de moyens, c'est-à-dire mettre en place des actions sans garantie de résultat</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="b" id="q8b">
                        <label for="q8b">Une obligation de prévention, incluant la lutte contre le harcèlement et les violences sexistes et sexuelles</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="c" id="q8c">
                        <label for="q8c">Une obligation de résultat, c'est-à-dire garantir l'absence totale de harcèlement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="d" id="q8d">
                        <label for="q8d">Une obligation de formation annuelle pour tous les agents</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q8', 'b', 'L\'article L. 136-1 du Code général de la fonction publique impose aux employeurs publics une obligation de prévention en matière de santé mentale. Cela inclut la mise en place de mesures pour prévenir et lutter contre le harcèlement moral et sexuel, ainsi que les violences sexistes et sexuelles.')">✓ Valider cette réponse</button>
                <div id="feedback8" class="feedback"></div>
            </div>
            
            <!-- Question 9 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Quel texte fondateur interdit explicitement le harcèlement moral et sexuel dans la fonction publique, posant ainsi les bases de la protection des agents ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q9" value="a" id="q9a">
                        <label for="q9a">La loi du 13 juillet 1983</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q9" value="b" id="q9b">
                        <label for="q9b">Le Code pénal</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q9" value="c" id="q9c">
                        <label for="q9c">Le Code du travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q9" value="d" id="q9d">
                        <label for="q9d">La Charte de la DGAFP</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q9', 'a', 'La loi du 13 juillet 1983 est le texte fondateur qui interdit explicitement le harcèlement moral et sexuel dans la fonction publique. Elle pose les bases légales de la protection des agents contre ces agissements, complétée ensuite par des lois et décrets ultérieurs.')">✓ Valider cette réponse</button>
                <div id="feedback9" class="feedback"></div>
            </div>
            
            <!-- Question 10 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">Quel principe, consacré par la loi du 6 août 2019, est au cœur de la lutte contre le harcèlement dans les collectivités territoriales, imposant aux employeurs publics de mettre en place des mesures actives pour prévenir ces agissements ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q10" value="a" id="q10a">
                        <label for="q10a">Le principe de précaution</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="b" id="q10b">
                        <label for="q10b">Le principe de prévention</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="c" id="q10c">
                        <label for="q10c">Le principe de confidentialité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="d" id="q10d">
                        <label for="q10d">Le principe de proportionnalité</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q10', 'b', 'Le principe de prévention est au cœur de la loi du 6 août 2019. Cette loi impose aux employeurs publics de mettre en place des mesures actives pour prévenir le harcèlement et les violences sexistes et sexuelles, plutôt que de simplement réagir une fois les faits commis.')">✓ Valider cette réponse</button>
                <div id="feedback10" class="feedback"></div>
            </div>
        </div>

        <!-- Thématique 2 : Dispositifs de signalement -->
        <div id="theme2" class="theme">
            <h2>📋 2. Dispositifs de signalement</h2>
            
            <!-- Question 11 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">Depuis quelle date les collectivités territoriales sont-elles tenues de mettre en place un dispositif complet de signalement des actes de harcèlement, conformément au décret du 13 mars 2020 ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q11" value="a" id="q11a">
                        <label for="q11a">1er mai 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q11" value="b" id="q11b">
                        <label for="q11b">1er mai 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q11" value="c" id="q11c">
                        <label for="q11c">1er février 2025</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q11" value="d" id="q11d">
                        <label for="q11d">1er janvier 2023</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q11', 'b', 'Le décret du 13 mars 2020 a imposé aux collectivités territoriales de mettre en place un dispositif complet de signalement des actes de harcèlement à compter du 1er mai 2020. Ce décret a marqué une première étape décisive dans la structuration des procédures de signalement.')">✓ Valider cette réponse</button>
                <div id="feedback11" class="feedback"></div>
            </div>
            
            <!-- Question 12 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Combien de procédures distinctes et complémentaires le dispositif de signalement des actes de harcèlement doit-il obligatoirement comporter, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q12" value="a" id="q12a">
                        <label for="q12a">Une procédure unique de signalement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q12" value="b" id="q12b">
                        <label for="q12b">Deux procédures : recueil des signalements et traitement des faits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q12" value="c" id="q12c">
                        <label for="q12c">Trois procédures : recueil des signalements, orientation des victimes, et traitement des faits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q12" value="d" id="q12d">
                        <label for="q12d">Quatre procédures, incluant une procédure de médiation obligatoire</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q12', 'c', 'Le dispositif de signalement doit obligatoirement comporter trois procédures distinctes et complémentaires : une procédure de recueil des signalements, une procédure d\'orientation des agents victimes vers les services compétents, et une procédure d\'orientation vers les autorités pour le traitement des faits.')">✓ Valider cette réponse</button>
                <div id="feedback12" class="feedback"></div>
            </div>
            
            <!-- Question 13 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Quels sont les différents canaux par lesquels un agent victime ou témoin de harcèlement peut signaler les faits dans une collectivité territoriale ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q13" value="a" id="q13a">
                        <label for="q13a">Uniquement le référent harcèlement désigné dans la collectivité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q13" value="b" id="q13b">
                        <label for="q13b">Plusieurs canaux, incluant le référent harcèlement, le supérieur hiérarchique, les représentants du personnel, et le médecin de prévention</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q13" value="c" id="q13c">
                        <label for="q13c">Uniquement le référent harcèlement et le supérieur hiérarchique direct</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q13" value="d" id="q13d">
                        <label for="q13d">Uniquement le Défenseur des droits</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q13', 'b', 'Les agents disposent de multiples canaux pour signaler les faits de harcèlement. Ils peuvent s\'adresser au référent harcèlement, à leur supérieur hiérarchique, aux représentants du personnel (Comité Social Territorial), ou encore au médecin de prévention. Cette multiplicité vise à faciliter la libération de la parole.')">✓ Valider cette réponse</button>
                <div id="feedback13" class="feedback"></div>
            </div>
            
            <!-- Question 14 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">Quel principe fondamental doit être garanti tout au long de la procédure de signalement des actes de harcèlement, afin de protéger les agents et encourager les signalements ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q14" value="a" id="q14a">
                        <label for="q14a">Le principe de publicité des signalements</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q14" value="b" id="q14b">
                        <label for="q14b">Le principe de transparence totale</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q14" value="c" id="q14c">
                        <label for="q14c">Le principe de confidentialité de l'identité des signataires et des personnes mises en cause</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q14" value="d" id="q14d">
                        <label for="q14d">Le principe de rapidité absolue du traitement</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q14', 'c', 'Le principe de confidentialité doit être strictement garanti tout au long de la procédure de signalement. Cela signifie que l\'identité de l\'agent qui signale les faits, ainsi que celle des personnes mises en cause, ne peut être divulguée, sauf aux personnes ayant besoin d\'en connaître pour le traitement du signalement.')">✓ Valider cette réponse</button>
                <div id="feedback14" class="feedback"></div>
            </div>
            
            <!-- Question 15 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Quel document, publié par la Direction générale de l'administration et de la fonction publique (DGAFP), encadre le fonctionnement des dispositifs de signalement et de traitement des situations de harcèlement dans les collectivités territoriales ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q15" value="a" id="q15a">
                        <label for="q15a">La circulaire de lutte contre le harcèlement publiée en 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q15" value="b" id="q15b">
                        <label for="q15b">La Charte de fonctionnement des dispositifs de signalement, publiée en novembre 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q15" value="c" id="q15c">
                        <label for="q15c">Le Code déontologique de la fonction publique territoriale</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q15" value="d" id="q15d">
                        <label for="q15d">Le Code du travail</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q15', 'b', 'La Charte de fonctionnement des dispositifs de signalement et de traitement des situations de violences sexuelles, de discrimination, de harcèlement sexuel ou moral, et d\'agissements sexistes, publiée par la DGAFP en novembre 2019, constitue un référentiel essentiel pour les employeurs publics.')">✓ Valider cette réponse</button>
                <div id="feedback15" class="feedback"></div>
            </div>
            
            <!-- Question 16 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">En quoi consiste la mutualisation des dispositifs de signalement entre collectivités territoriales, telle que prévue par le décret du 6 novembre 2024 ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q16" value="a" id="q16a">
                        <label for="q16a">À centraliser tous les signalements au niveau national pour une gestion unique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q16" value="b" id="q16b">
                        <label for="q16b">À permettre aux petites collectivités, qui ne disposent pas de ressources internes suffisantes, de bénéficier d'un dispositif professionnel et sécurisé via les centres de gestion ou en partenariat avec d'autres collectivités</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q16" value="c" id="q16c">
                        <label for="q16c">À supprimer les référents harcèlement dans les petites collectivités</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q16" value="d" id="q16d">
                        <label for="q16d">À externaliser la gestion des signalements vers des entreprises privées spécialisées</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q16', 'b', 'La mutualisation des dispositifs de signalement permet aux petites collectivités, qui ne disposent pas toujours de ressources internes suffisantes, de bénéficier d\'un dispositif professionnel et sécurisé. Cela peut se faire via les centres de gestion ou en partenariat avec d\'autres collectivités.')">✓ Valider cette réponse</button>
                <div id="feedback16" class="feedback"></div>
            </div>
            
            <!-- Question 17 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Quel acteur, parmi les suivants, est spécifiquement chargé d'orienter un agent victime de harcèlement vers les services compétents (médecine préventive, service social, associations spécialisées) ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q17" value="a" id="q17a">
                        <label for="q17a">Le maire de la collectivité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q17" value="b" id="q17b">
                        <label for="q17b">Le référent harcèlement désigné dans la collectivité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q17" value="c" id="q17c">
                        <label for="q17c">Le préfet du département</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q17" value="d" id="q17d">
                        <label for="q17d">Le procureur de la République</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q17', 'b', 'Le référent harcèlement, désigné dans chaque collectivité, a pour mission d\'orienter les agents victimes vers les services compétents, tels que la médecine préventive, le service social du personnel, ou les associations spécialisées dans l\'accompagnement des victimes.')">✓ Valider cette réponse</button>
                <div id="feedback17" class="feedback"></div>
            </div>
            
            <!-- Question 18 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Quel décret, entré en vigueur en 2025, a abrogé et remplacé le décret du 13 mars 2020 pour moderniser le système de signalement des actes de harcèlement dans les collectivités territoriales ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q18" value="a" id="q18a">
                        <label for="q18a">Le décret du 4 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q18" value="b" id="q18b">
                        <label for="q18b">Le décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q18" value="c" id="q18c">
                        <label for="q18c">Le décret du 30 juillet 1987</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q18" value="d" id="q18d">
                        <label for="q18d">Le décret du 28 mai 2025</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q18', 'b', 'Le décret du 6 novembre 2024, entré en vigueur le 1er février 2025, a abrogé et remplacé le décret du 13 mars 2020. Il a modernisé le système de signalement en renforçant les exigences de confidentialité, en précisant les procédures de traitement avec des délais contraignants, et en permettant la mutualisation des dispositifs.')">✓ Valider cette réponse</button>
                <div id="feedback18" class="feedback"></div>
            </div>
            
            <!-- Question 19 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Quel principe doit guider l'orientation des agents victimes de harcèlement vers les services compétents, afin de garantir un accompagnement adapté et respectueux ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q19" value="a" id="q19a">
                        <label for="q19a">Le principe d'égalité de traitement entre tous les agents</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q19" value="b" id="q19b">
                        <label for="q19b">Le principe de bienveillance, pour tenir compte de la souffrance psychique des victimes</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q19" value="c" id="q19c">
                        <label for="q19c">Le principe de neutralité absolue, sans prise en compte des spécificités de chaque situation</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q19" value="d" id="q19d">
                        <label for="q19d">Le principe de rapidité, même au détriment de la qualité de l'accompagnement</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q19', 'b', 'Le principe de bienveillance doit guider l\'orientation des agents victimes. Les professionnels en charge de cette orientation doivent tenir compte de la souffrance psychique des victimes et adopter une posture empathique, tout en conservant la neutralité nécessaire à l\'objectivité du traitement des signalements.')">✓ Valider cette réponse</button>
                <div id="feedback19" class="feedback"></div>
            </div>
            
            <!-- Question 20 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">Quels types de documents peuvent être utilisés comme preuves dans le cadre d'un signalement ou d'une enquête administrative pour harcèlement ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q20" value="a" id="q20a">
                        <label for="q20a">Uniquement les certificats médicaux attestant d'un état de stress ou de dépression</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q20" value="b" id="q20b">
                        <label for="q20b">Uniquement les messages électroniques ou SMS envoyés par l'auteur présumé des faits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q20" value="c" id="q20c">
                        <label for="q20c">Uniquement les témoignages écrits des collègues directs de la victime</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q20" value="d" id="q20d">
                        <label for="q20d">Tous ces documents, ainsi que d'autres éléments comme les procès-verbaux d'audition, les enregistrements audio ou vidéo (légalement obtenus), ou les constatations matérielles</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q20', 'd', 'Les preuves dans le cadre d\'un signalement ou d\'une enquête administrative pour harcèlement peuvent être variées. Elles incluent les messages électroniques, les SMS, les certificats médicaux, les témoignages, les procès-verbaux d\'audition, les enregistrements audio ou vidéo (légalement obtenus), ainsi que les constatations matérielles effectuées sur les lieux de travail.')">✓ Valider cette réponse</button>
                <div id="feedback20" class="feedback"></div>
            </div>
        </div>

        <!-- Thématique 3 : Enquête administrative -->
        <div id="theme3" class="theme">
            <h2>🔍 3. Enquête administrative et rôle des instances</h2>
            
            <!-- Question 21 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">Selon l'article 6 ter de la loi du 13 juillet 1983, quelle procédure doit obligatoirement être engagée dès qu'un agent informe son autorité territoriale de faits de harcèlement ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q21" value="a" id="q21a">
                        <label for="q21a">Une procédure de médiation interne</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q21" value="b" id="q21b">
                        <label for="q21b">Une enquête administrative</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q21" value="c" id="q21c">
                        <label for="q21c">Une procédure disciplinaire immédiate contre l'auteur présumé</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q21" value="d" id="q21d">
                        <label for="q21d">Une procédure de licenciement pour faute grave</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q21', 'b', 'Dès qu\'un agent informe son autorité territoriale de faits de harcèlement, une enquête administrative doit obligatoirement être diligentée, conformément à l\'article 6 ter de la loi du 13 juillet 1983. Cette enquête vise à établir la matérialité des faits et à qualifier juridiquement les comportements reprochés.')">✓ Valider cette réponse</button>
                <div id="feedback21" class="feedback"></div>
            </div>
            
            <!-- Question 22 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Quelles qualités doivent impérativement présenter les personnes chargées de mener une enquête administrative en cas de harcèlement, selon les recommandations du Défenseur des droits ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q22" value="a" id="q22a">
                        <label for="q22a">Elles doivent être des agents de la collectivité depuis au moins 10 ans</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q22" value="b" id="q22b">
                        <label for="q22b">Elles doivent être formées, compétentes et impartiales, sans lien personnel ou professionnel avec l'agent mis en cause</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q22" value="c" id="q22c">
                        <label for="q22c">Elles doivent obligatoirement être des magistrats ou des avocats</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q22" value="d" id="q22d">
                        <label for="q22d">Elles doivent être désignées par tirage au sort parmi les agents de la collectivité</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q22', 'b', 'Les enquêteurs doivent impérativement être formés, compétents et impartials. Ils ne doivent pas avoir eu de différend personnel ou professionnel avec l\'agent mis en cause, ni entretenir avec lui des relations susceptibles de faire douter de leur objectivité. Le Défenseur des droits a insisté sur la nécessité de garantir ces qualités pour assurer la crédibilité de l\'enquête.')">✓ Valider cette réponse</button>
                <div id="feedback22" class="feedback"></div>
            </div>
            
            <!-- Question 23 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Quels types de preuves peuvent être recueillis dans le cadre d'une enquête administrative pour harcèlement, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q23" value="a" id="q23a">
                        <label for="q23a">Uniquement des preuves directes, comme des messages ou des enregistrements</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q23" value="b" id="q23b">
                        <label for="q23b">Uniquement des preuves indirectes, comme des certificats médicaux ou des témoignages</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q23" value="c" id="q23c">
                        <label for="q23c">Des preuves directes et indirectes, incluant messages, témoignages, certificats médicaux, et constatations matérielles</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q23" value="d" id="q23d">
                        <label for="q23d">Uniquement des preuves matérielles, comme des photographies ou des enregistrements vidéo</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q23', 'c', 'Les preuves recueillies dans le cadre d\'une enquête administrative pour harcèlement peuvent être à la fois directes et indirectes. Cela inclut des messages électroniques, des SMS, des certificats médicaux, des témoignages, des enregistrements (légalement obtenus), et des constatations matérielles.')">✓ Valider cette réponse</button>
                <div id="feedback23" class="feedback"></div>
            </div>
            
            <!-- Question 24 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">Quel organisme a recommandé, dans une décision du 20 avril 2020, de mieux encadrer les conditions de déroulement des enquêtes internes pour garantir la compétence et l'impartialité des enquêteurs ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q24" value="a" id="q24a">
                        <label for="q24a">Le Conseil d'État</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q24" value="b" id="q24b">
                        <label for="q24b">Le Défenseur des droits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q24" value="c" id="q24c">
                        <label for="q24c">La Direction générale de l'administration et de la fonction publique (DGAFP)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q24" value="d" id="q24d">
                        <label for="q24d">Le Tribunal administratif de Paris</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q24', 'b', 'Le Défenseur des droits a recommandé, dans sa décision du 20 avril 2020, de mieux encadrer les conditions de déroulement des enquêtes internes. Il a souligné la nécessité de s\'assurer que les enquêteurs présentent les garanties de compétence et d\'impartialité requises.')">✓ Valider cette réponse</button>
                <div id="feedback24" class="feedback"></div>
            </div>
            
            <!-- Question 25 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Quel est l'objectif principal d'une enquête administrative en cas de signalement de harcèlement, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q25" value="a" id="q25a">
                        <label for="q25a">Sanctionner immédiatement l'auteur présumé des faits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q25" value="b" id="q25b">
                        <label for="q25b">Établir la matérialité des faits allégués et qualifier juridiquement les comportements reprochés</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q25" value="c" id="q25c">
                        <label for="q25c">Classer sans suite le signalement si les faits ne sont pas immédiatement prouvés</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q25" value="d" id="q25d">
                        <label for="q25d">Publier les résultats de l'enquête pour dissuader d'autres agissements</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q25', 'b', 'L\'objectif principal d\'une enquête administrative en cas de signalement de harcèlement est d\'établir la matérialité des faits allégués et de qualifier juridiquement les comportements reprochés. Cela permet de déterminer si les faits constituent effectivement du harcèlement moral, sexuel, ou d\'autres violations des obligations statutaires.')">✓ Valider cette réponse</button>
                <div id="feedback25" class="feedback"></div>
            </div>
            
            <!-- Question 26 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">Quelle posture les enquêteurs doivent-ils adopter lors des auditions des victimes présumées de harcèlement, selon les recommandations de la Direction générale du travail ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q26" value="a" id="q26a">
                        <label for="q26a">Une posture de neutralité absolue, sans tenir compte de la souffrance psychique des victimes</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q26" value="b" id="q26b">
                        <label for="q26b">Une posture de bienveillance, en tenant compte de la souffrance psychique des victimes tout en conservant une distance nécessaire à l'objectivité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q26" value="c" id="q26c">
                        <label for="q26c">Une posture de confrontation, pour mettre en difficulté les déclarations des victimes</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q26" value="d" id="q26d">
                        <label for="q26d">Une posture de rapidité, en limitant le temps des auditions pour accélérer le traitement des dossiers</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q26', 'b', 'Les enquêteurs doivent adopter une posture de bienveillance lors des auditions des victimes présumées. Ils doivent tenir compte de la souffrance psychique des victimes, tout en conservant la distance et la neutralité nécessaires à l\'objectivité de l\'enquête.')">✓ Valider cette réponse</button>
                <div id="feedback26" class="feedback"></div>
            </div>
            
            <!-- Question 27 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Quel document doit être rédigé après chaque audition dans le cadre d'une enquête administrative pour harcèlement, afin de garantir la valeur probante des témoignages ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q27" value="a" id="q27a">
                        <label for="q27a">Un rapport d'étonnement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q27" value="b" id="q27b">
                        <label for="q27b">Un procès-verbal d'audition, dûment signé par les personnes entendues et les enquêteurs</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q27" value="c" id="q27c">
                        <label for="q27c">Une main courante</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q27" value="d" id="q27d">
                        <label for="q27d">Une note interne confidentielle</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q27', 'b', 'Un procès-verbal d\'audition doit être rédigé après chaque audition et signé par les personnes entendues ainsi que par les enquêteurs. Ce document confère une valeur probante aux témoignages en cas de procédure disciplinaire ultérieure.')">✓ Valider cette réponse</button>
                <div id="feedback27" class="feedback"></div>
            </div>
            
            <!-- Question 28 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Quelle instance représentative du personnel peut être associée à une enquête administrative en cas de harcèlement, selon les dispositions de la loi du 6 août 2019 ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q28" value="a" id="q28a">
                        <label for="q28a">Le Comité Social Territorial (CST) ou sa Formation Spécialisée en matière de Santé, Sécurité et Conditions de Travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q28" value="b" id="q28b">
                        <label for="q28b">Le Comité d'entreprise</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q28" value="c" id="q28c">
                        <label for="q28c">Le CHSCT (Comité d'Hygiène, de Sécurité et des Conditions de Travail)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q28" value="d" id="q28d">
                        <label for="q28d">Le Comité technique paritaire</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q28', 'a', 'Le Comité Social Territorial (CST) ou sa Formation Spécialisée en matière de Santé, Sécurité et Conditions de Travail peut être associé à une enquête administrative en cas de harcèlement. Cette instance a été créée par la loi du 6 août 2019 pour remplacer les anciennes instances représentatives.')">✓ Valider cette réponse</button>
                <div id="feedback28" class="feedback"></div>
            </div>
            
            <!-- Question 29 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Quel texte a réorganisé les instances représentatives du personnel dans la fonction publique territoriale, en fusionnant les anciens Comités Techniques et les Comités d'Hygiène, de Sécurité et des Conditions de Travail ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q29" value="a" id="q29a">
                        <label for="q29a">La loi du 6 août 2019 de transformation de la fonction publique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q29" value="b" id="q29b">
                        <label for="q29b">Le décret du 13 mars 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q29" value="c" id="q29c">
                        <label for="q29c">Le Code du travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q29" value="d" id="q29d">
                        <label for="q29d">La Charte de la DGAFP</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q29', 'a', 'La loi du 6 août 2019 de transformation de la fonction publique a réorganisé les instances représentatives du personnel. Elle a fusionné les anciens Comités Techniques et les Comités d\'Hygiène, de Sécurité et des Conditions de Travail (CHSCT) pour créer le Comité Social Territorial (CST).')">✓ Valider cette réponse</button>
                <div id="feedback29" class="feedback"></div>
            </div>
            
            <!-- Question 30 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">Quel est le rôle de la Formation Spécialisée en matière de Santé, Sécurité et Conditions de Travail au sein du Comité Social Territorial ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q30" value="a" id="q30a">
                        <label for="q30a">Gérer les carrières des agents</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q30" value="b" id="q30b">
                        <label for="q30b">Exercer un droit d'alerte en cas de danger grave et imminent pour la santé ou la sécurité des agents, et proposer des mesures de prévention</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q30" value="c" id="q30c">
                        <label for="q30c">Négocier les salaires et les primes des agents</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q30" value="d" id="q30d">
                        <label for="q30d">Recruter les agents et gérer les mutations</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q30', 'b', 'La Formation Spécialisée en matière de Santé, Sécurité et Conditions de Travail dispose d\'un droit d\'alerte lorsqu\'elle constate l\'existence d\'une cause de danger grave et imminent pour la santé ou la sécurité des agents. Elle peut également proposer des mesures de prévention à l\'autorité territoriale.')">✓ Valider cette réponse</button>
                <div id="feedback30" class="feedback"></div>
            </div>
        </div>

        <!-- Thématique 4 : Protection fonctionnelle -->
        <div id="theme4" class="theme">
            <h2>🛡️ 4. Protection fonctionnelle</h2>
            
            <!-- Question 31 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">Quels types de frais sont intégralement pris en charge par la protection fonctionnelle pour un agent victime de harcèlement, selon les articles L. 134-1 et suivants du Code général de la fonction publique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q31" value="a" id="q31a">
                        <label for="q31a">Les frais de transport et de restauration</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q31" value="b" id="q31b">
                        <label for="q31b">Les frais d'avocat, selon des modalités définies par convention</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q31" value="c" id="q31c">
                        <label for="q31c">Les frais de logement et de déplacement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q31" value="d" id="q31d">
                        <label for="q31d">Les frais de formation professionnelle</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q31', 'b', 'La protection fonctionnelle garantit la prise en charge intégrale des frais d\'avocat pour les agents victimes de harcèlement. Une convention doit être signée entre la collectivité employeur et l\'avocat choisi par l\'agent, déterminant le montant des honoraires.')">✓ Valider cette réponse</button>
                <div id="feedback31" class="feedback"></div>
            </div>
            
            <!-- Question 32 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Quel texte encadre spécifiquement la protection fonctionnelle des agents publics victimes de harcèlement, en précisant les modalités de prise en charge des frais d'avocat et d'accompagnement ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q32" value="a" id="q32a">
                        <label for="q32a">Les articles L. 134-1 et suivants du Code général de la fonction publique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q32" value="b" id="q32b">
                        <label for="q32b">La loi du 13 juillet 1983</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q32" value="c" id="q32c">
                        <label for="q32c">Le décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q32" value="d" id="q32d">
                        <label for="q32d">La Charte de la DGAFP</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q32', 'a', 'Les articles L. 134-1 et suivants du Code général de la fonction publique encadrent la protection fonctionnelle. Ils précisent notamment les modalités de prise en charge des frais d\'avocat et d\'accompagnement psychologique pour les agents victimes.')">✓ Valider cette réponse</button>
                <div id="feedback32" class="feedback"></div>
            </div>
            
            <!-- Question 33 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Qui bénéficie automatiquement de la protection fonctionnelle en cas de harcèlement dans les collectivités territoriales, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q33" value="a" id="q33a">
                        <label for="q33a">Uniquement les agents victimes de harcèlement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q33" value="b" id="q33b">
                        <label for="q33b">Les agents victimes, les témoins des faits, et les lanceurs d'alerte</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q33" value="c" id="q33c">
                        <label for="q33c">Uniquement les agents ayant déposé une plainte pénale</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q33" value="d" id="q33d">
                        <label for="q33d">Uniquement les agents en CDI</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q33', 'b', 'La protection fonctionnelle s\'étend aux agents victimes de harcèlement, mais aussi aux témoins des faits et aux lanceurs d\'alerte. Cette extension vise à éviter toute mesure de rétorsion susceptible de décourager la dénonciation des agissements répréhensibles.')">✓ Valider cette réponse</button>
                <div id="feedback33" class="feedback"></div>
            </div>
            
            <!-- Question 34 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">Quel document doit obligatoirement être signé entre la collectivité employeur et l'avocat choisi par un agent protégé, pour déterminer les modalités de prise en charge des frais de défense ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q34" value="a" id="q34a">
                        <label for="q34a">Une convention</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q34" value="b" id="q34b">
                        <label for="q34b">Un contrat de travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q34" value="c" id="q34c">
                        <label for="q34c">Un procès-verbal</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q34" value="d" id="q34d">
                        <label for="q34d">Une main courante</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q34', 'a', 'Une convention doit obligatoirement être signée entre la collectivité employeur et l\'avocat choisi par l\'agent protégé. Ce document détermine le montant des honoraires, selon un tarif horaire ou un forfait global pour l\'ensemble de la procédure.')">✓ Valider cette réponse</button>
                <div id="feedback34" class="feedback"></div>
            </div>
            
            <!-- Question 35 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Quel principe, énoncé à l'article L. 133-3 du Code général de la fonction publique, interdit toute forme de représailles à l'encontre des victimes, des témoins et des lanceurs d'alerte ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q35" value="a" id="q35a">
                        <label for="q35a">Le principe de précaution</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q35" value="b" id="q35b">
                        <label for="q35b">Le principe de non-discrimination et de protection contre les représailles</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q35" value="c" id="q35c">
                        <label for="q35c">Le principe de confidentialité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q35" value="d" id="q35d">
                        <label for="q35d">Le principe de proportionnalité</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q35', 'b', 'L\'article L. 133-3 du Code général de la fonction publique établit un principe absolu de protection contre toute forme de représailles à l\'encontre des victimes, des témoins et des lanceurs d\'alerte. Aucune mesure discriminatoire ne peut être prise contre eux.')">✓ Valider cette réponse</button>
                <div id="feedback35" class="feedback"></div>
            </div>
            
            <!-- Question 36 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">Quelle décision du Conseil constitutionnel, rendue en 2024, a abrogé l'article L. 134-4 du Code général de la fonction publique, qui prévoyait que l'agent devait rembourser les sommes perçues au titre de la protection fonctionnelle s'il était ultérieurement reconnu coupable ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q36" value="a" id="q36a">
                        <label for="q36a">Décision n° 2024-1098 QPC du 4 juillet 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q36" value="b" id="q36b">
                        <label for="q36b">Décision n° 2020-800 QPC du 18 décembre 2020</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q36" value="c" id="q36c">
                        <label for="q36c">Décision n° 2019-778 QPC du 21 mars 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q36" value="d" id="q36d">
                        <label for="q36d">Décision n° 2023-1000 QPC du 10 mai 2023</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q36', 'a', 'La décision n° 2024-1098 QPC du 4 juillet 2024 du Conseil constitutionnel a déclaré contraire à la Constitution l\'article L. 134-4 du Code général de la fonction publique. Cet article prévoyait que l\'agent devait rembourser les sommes perçues au titre de la protection fonctionnelle s\'il était ultérieurement reconnu coupable.')">✓ Valider cette réponse</button>
                <div id="feedback36" class="feedback"></div>
            </div>
            
            <!-- Question 37 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Quels types de soutien la protection fonctionnelle garantit-elle aux agents victimes de harcèlement, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q37" value="a" id="q37a">
                        <label for="q37a">Uniquement un soutien psychologique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q37" value="b" id="q37b">
                        <label for="q37b">Uniquement un soutien juridique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q37" value="c" id="q37c">
                        <label for="q37c">Un soutien psychologique, juridique et financier</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q37" value="d" id="q37d">
                        <label for="q37d">Uniquement un soutien financier pour les frais de justice</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q37', 'c', 'La protection fonctionnelle garantit aux agents victimes de harcèlement un soutien psychologique, un soutien juridique (prise en charge des frais d\'avocat), et un soutien financier pour la réparation intégrale de leur préjudice, tant matériel que moral.')">✓ Valider cette réponse</button>
                <div id="feedback37" class="feedback"></div>
            </div>
            
            <!-- Question 38 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Dans quel cas la protection fonctionnelle peut-elle être accordée à titre conservatoire, selon l'article L. 134-6 du Code général de la fonction publique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q38" value="a" id="q38a">
                        <label for="q38a">En cas de plainte pénale déposée par la victime</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q38" value="b" id="q38b">
                        <label for="q38b">En cas de risque manifeste d'atteinte grave à l'intégrité physique de l'agent</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q38" value="c" id="q38c">
                        <label for="q38c">En cas de sanction disciplinaire prononcée contre l'auteur présumé</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q38" value="d" id="q38d">
                        <label for="q38d">En cas de mutation de l'agent victime</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q38', 'b', 'La protection fonctionnelle peut être accordée à titre conservatoire lorsque l\'administration est informée de l\'existence d\'un risque manifeste d\'atteinte grave à l\'intégrité physique de l\'agent. Des mesures d\'urgence doivent alors être prises sans délai.')">✓ Valider cette réponse</button>
                <div id="feedback38" class="feedback"></div>
            </div>
            
            <!-- Question 39 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Quel texte interdit expressément toute mesure discriminatoire ou représailles à l'encontre d'un agent ayant signalé de bonne foi des faits de harcèlement, même si ces faits ne sont pas finalement établis ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q39" value="a" id="q39a">
                        <label for="q39a">Article L. 135-4 du Code général de la fonction publique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q39" value="b" id="q39b">
                        <label for="q39b">Loi Sapin II du 9 décembre 2016</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q39" value="c" id="q39c">
                        <label for="q39c">Décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q39" value="d" id="q39d">
                        <label for="q39d">Charte de la DGAFP</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q39', 'a', 'L\'article L. 135-4 du Code général de la fonction publique interdit expressément toute mesure discriminatoire ou représailles à l\'encontre d\'un agent ayant signalé de bonne foi des faits de harcèlement, même si ces faits ne sont pas finalement établis.')">✓ Valider cette réponse</button>
                <div id="feedback39" class="feedback"></div>
            </div>
            
            <!-- Question 40 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">Quelle loi, adoptée en 2022, a considérablement renforcé la protection des lanceurs d'alerte en instaurant un régime de présomption probatoire favorable à l'agent qui s'estime victime de représailles ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q40" value="a" id="q40a">
                        <label for="q40a">Loi du 6 août 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q40" value="b" id="q40b">
                        <label for="q40b">Loi n° 2022-401 du 21 mars 2022</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q40" value="c" id="q40c">
                        <label for="q40c">Loi du 13 juillet 1983</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q40" value="d" id="q40d">
                        <label for="q40d">Décret du 13 mars 2020</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q40', 'b', 'La loi n° 2022-401 du 21 mars 2022 a renforcé la protection des lanceurs d\'alerte en instaurant un régime de présomption probatoire. Désormais, dès que le requérant présente des éléments de fait permettant de supposer qu\'il a signalé des faits de harcèlement, il incombe à l\'employeur de prouver que la décision contestée est justifiée par des éléments objectifs.')">✓ Valider cette réponse</button>
                <div id="feedback40" class="feedback"></div>
            </div>
        </div>

        <!-- Thématique 5 : Sanctions et recours -->
        <div id="theme5" class="theme">
            <h2>⚖️ 5. Sanctions et recours</h2>
            
            <!-- Question 41 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">Quelle est la sanction disciplinaire la plus grave pouvant être prononcée contre un agent auteur de harcèlement moral ou sexuel dans la fonction publique territoriale, selon les textes en vigueur ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q41" value="a" id="q41a">
                        <label for="q41a">L'avertissement</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q41" value="b" id="q41b">
                        <label for="q41b">Le blâme</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q41" value="c" id="q41c">
                        <label for="q41c">La révocation, entraînant l'exclusion définitive de la fonction publique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q41" value="d" id="q41d">
                        <label for="q41d">L'exclusion temporaire de fonctions pour une durée maximale de 15 jours</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q41', 'c', 'La révocation est la sanction disciplinaire la plus grave dans la fonction publique territoriale. Elle entraîne l\'exclusion définitive de la fonction publique et la radiation des cadres.')">✓ Valider cette réponse</button>
                <div id="feedback41" class="feedback"></div>
            </div>
            
            <!-- Question 42 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Quel principe fondamental doit guider le choix de la sanction disciplinaire en cas de harcèlement, selon la jurisprudence administrative ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q42" value="a" id="q42a">
                        <label for="q42a">Le principe de rapidité, pour sanctionner au plus vite</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q42" value="b" id="q42b">
                        <label for="q42b">Le principe de proportionnalité, pour adapter la sanction à la gravité des faits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q42" value="c" id="q42c">
                        <label for="q42c">Le principe de confidentialité, pour éviter toute publicité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q42" value="d" id="q42d">
                        <label for="q42d">Le principe de publicité, pour dissuader d'autres agissements</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q42', 'b', 'Le principe de proportionnalité est essentiel dans le choix de la sanction disciplinaire. L\'autorité disciplinaire doit apprécier la gravité de la faute commise et déterminer une sanction adaptée, en tenant compte des circonstances de l\'affaire et des antécédents de l\'agent.')">✓ Valider cette réponse</button>
                <div id="feedback42" class="feedback"></div>
            </div>
            
            <!-- Question 43 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Quelle instance peut décider de publier les sanctions disciplinaires prononcées contre des agents auteurs de harcèlement, afin de renforcer l'effet dissuasif ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q43" value="a" id="q43a">
                        <label for="q43a">Le Comité Social Territorial</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q43" value="b" id="q43b">
                        <label for="q43b">L'autorité investie du pouvoir disciplinaire, après avis du conseil de discipline</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q43" value="c" id="q43c">
                        <label for="q43c">Le Défenseur des droits</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q43" value="d" id="q43d">
                        <label for="q43d">Le procureur de la République</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q43', 'b', 'L\'autorité investie du pouvoir disciplinaire peut décider de publier les sanctions disciplinaires prononcées, après avis du conseil de discipline. Cette mesure vise à renforcer l\'effet dissuasif et à démontrer que les signalements sont traités.')">✓ Valider cette réponse</button>
                <div id="feedback43" class="feedback"></div>
            </div>
            
            <!-- Question 44 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">Quelles sont les peines encourues par un agent auteur de harcèlement sexuel dans le cadre professionnel, selon l'article 222-33 du Code pénal ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q44" value="a" id="q44a">
                        <label for="q44a">1 an d'emprisonnement et 15 000 € d'amende</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q44" value="b" id="q44b">
                        <label for="q44b">2 ans d'emprisonnement et 30 000 € d'amende</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q44" value="c" id="q44c">
                        <label for="q44c">3 ans d'emprisonnement et 45 000 € d'amende en cas de circonstances aggravantes</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q44" value="d" id="q44d">
                        <label for="q44d">5 ans d'emprisonnement et 75 000 € d'amende</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q44', 'b', 'Le harcèlement sexuel dans le cadre professionnel est puni de 2 ans d\'emprisonnement et 30 000 € d\'amende, selon l\'article 222-33 du Code pénal. En cas de circonstances aggravantes (comme l\'abus d\'autorité), la peine peut être portée à 3 ans d\'emprisonnement et 45 000 € d\'amende.')">✓ Valider cette réponse</button>
                <div id="feedback44" class="feedback"></div>
            </div>
            
            <!-- Question 45 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Quel texte encadre spécifiquement les sanctions disciplinaires applicables aux fonctionnaires territoriaux auteurs de harcèlement moral ou sexuel ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q45" value="a" id="q45a">
                        <label for="q45a">La loi n° 84-53 du 26 janvier 1984 portant dispositions statutaires relatives à la fonction publique territoriale</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q45" value="b" id="q45b">
                        <label for="q45b">Le décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q45" value="c" id="q45c">
                        <label for="q45c">La Charte de la DGAFP</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q45" value="d" id="q45d">
                        <label for="q45d">Le Code pénal</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q45', 'a', 'La loi n° 84-53 du 26 janvier 1984 encadre les sanctions disciplinaires applicables aux fonctionnaires territoriaux. Les auteurs de harcèlement moral ou sexuel s\'exposent à des sanctions pouvant aller jusqu\'à la révocation.')">✓ Valider cette réponse</button>
                <div id="feedback45" class="feedback"></div>
            </div>
            
            <!-- Question 46 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">Quel principe juridique, reconnu par le Tribunal des conflits en 2025, permet aux victimes de harcèlement de poursuivre simultanément l'agent harceleur et la collectivité employeur pour obtenir une réparation intégrale de leurs préjudices ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q46" value="a" id="q46a">
                        <label for="q46a">Le principe de précaution</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q46" value="b" id="q46b">
                        <label for="q46b">Le principe de cumul de responsabilités</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q46" value="c" id="q46c">
                        <label for="q46c">Le principe de confidentialité</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q46" value="d" id="q46d">
                        <label for="q46d">Le principe de proportionnalité</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q46', 'b', 'Le principe de cumul de responsabilités, reconnu par le Tribunal des conflits en 2025, permet aux victimes de harcèlement de poursuivre simultanément l\'agent harceleur (devant le juge judiciaire) et la collectivité employeur (devant le juge administratif). Cela offre une double voie d\'action pour obtenir une réparation intégrale des préjudices subis.')">✓ Valider cette réponse</button>
                <div id="feedback46" class="feedback"></div>
            </div>
            
            <!-- Question 47 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Quel recours juridique permet à un agent victime de harcèlement d'obtenir des mesures provisoires en urgence pour faire cesser une atteinte grave et manifestement illégale à une liberté fondamentale, comme le droit à la santé ou à la dignité ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q47" value="a" id="q47a">
                        <label for="q47a">Le référé-liberté devant le juge administratif</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q47" value="b" id="q47b">
                        <label for="q47b">Le recours en annulation</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q47" value="c" id="q47c">
                        <label for="q47c">Le recours en pleine juridiction</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q47" value="d" id="q47d">
                        <label for="q47d">Le recours en cassation</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q47', 'a', 'Le référé-liberté devant le juge administratif permet d\'obtenir des mesures provisoires en urgence pour faire cesser une atteinte grave et manifestement illégale à une liberté fondamentale, comme le droit à la santé ou à la dignité. Ce recours est particulièrement adapté aux situations de harcèlement.')">✓ Valider cette réponse</button>
                <div id="feedback47" class="feedback"></div>
            </div>
            
            <!-- Question 48 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Quelle décision jurisprudentielle, rendue en 2025, a reconnu pour la première fois le principe du cumul de responsabilités en matière de harcèlement, offrant ainsi aux victimes une double voie d'action ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q48" value="a" id="q48a">
                        <label for="q48a">Décision du Conseil d'État du 20 juin 2025</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q48" value="b" id="q48b">
                        <label for="q48b">Décision du Tribunal des conflits du 6 octobre 2025</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q48" value="c" id="q48c">
                        <label for="q48c">Décision du Tribunal administratif de Besançon du 6 juin 2025</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q48" value="d" id="q48d">
                        <label for="q48d">Décision du Conseil constitutionnel du 4 juillet 2024</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q48', 'b', 'La décision du Tribunal des conflits du 6 octobre 2025 a reconnu pour la première fois le principe du cumul de responsabilités en matière de harcèlement. Cette décision permet aux victimes de poursuivre simultanément l\'agent harceleur (responsabilité civile personnelle) et la collectivité employeur (responsabilité administrative).')">✓ Valider cette réponse</button>
                <div id="feedback48" class="feedback"></div>
            </div>
            
            <!-- Question 49 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Quel projet de loi, annoncé en 2025, vise à renforcer la protection des agents publics victimes de violences et de menaces dans l'exercice de leurs fonctions ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q49" value="a" id="q49a">
                        <label for="q49a">Projet de loi gouvernemental annoncé le 19 mai 2025</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q49" value="b" id="q49b">
                        <label for="q49b">Loi du 6 août 2019</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q49" value="c" id="q49c">
                        <label for="q49c">Décret du 6 novembre 2024</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q49" value="d" id="q49d">
                        <label for="q49d">Charte de la DGAFP</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q49', 'a', 'Un projet de loi gouvernemental a été annoncé le 19 mai 2025 pour renforcer la protection des agents publics victimes de violences et de menaces. Ce texte prévoit notamment l\'extension de la protection fonctionnelle aux proches des agents menacés et la création d\'un droit pour l\'administration de porter plainte au nom de l\'agent victime.')">✓ Valider cette réponse</button>
                <div id="feedback49" class="feedback"></div>
            </div>
            
            <!-- Question 50 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">Quelles mesures sont prévues par le projet de loi de 2025 pour accélérer les procédures judiciaires en matière de harcèlement et de violences commis sur des agents publics ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q50" value="a" id="q50a">
                        <label for="q50a">La création de chambres spécialisées au sein des tribunaux judiciaires</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q50" value="b" id="q50b">
                        <label for="q50b">La formation spécifique des magistrats et des personnels de greffe</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q50" value="c" id="q50c">
                        <label for="q50c">La définition d'objectifs de délais de jugement pour ces affaires</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q50" value="d" id="q50d">
                        <label for="q50d">Toutes ces mesures</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q50', 'd', 'Le projet de loi de 2025 prévoit plusieurs mesures pour accélérer les procédures judiciaires en matière de harcèlement et de violences commis sur des agents publics. Cela inclut la création de chambres spécialisées, la formation des magistrats, et la définition d\'objectifs de délais de jugement.')">✓ Valider cette réponse</button>
                <div id="feedback50" class="feedback"></div>
            </div>
        </div>

        <!-- Thématique 6 : Caractérisation juridique -->
        <div id="theme6" class="theme">
            <h2>📚 6. Caractérisation juridique du harcèlement</h2>
            
            <!-- Question 51 -->
            <div class="question-container">
                <span class="question-number">Question 1/10</span>
                <p class="question-text">L'article L. 133-3 du Code général de la fonction publique établit que l'interdiction du harcèlement moral et sexuel constitue une "garantie statutaire essentielle". En quoi cette qualification juridique est-elle significative pour la protection des agents publics ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q51" value="a" id="q51a">
                        <label for="q51a">Elle relève d'une simple directive administrative sans portée normative réelle</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q51" value="b" id="q51b">
                        <label for="q51b">Elle instaure un principe général de prévention sans obligation de résultat pour l'employeur</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q51" value="c" id="q51c">
                        <label for="q51c">Elle élève cette interdiction au rang de droit fondamental inhérent au statut de fonctionnaire, créant ainsi une obligation renforcée de protection</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q51" value="d" id="q51d">
                        <label for="q51d">Elle limite cette protection aux seuls fonctionnaires titulaires, excluant les agents contractuels</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q51', 'c', 'La qualification de garantie statutaire essentielle confère à l\'interdiction du harcèlement un caractère fondamental dans le statut des agents publics. Cela crée une obligation renforcée pour l\'employeur public et fonde un droit subjectif pour l\'agent, avec des conséquences sur le régime de preuve et les sanctions.')">✓ Valider cette réponse</button>
                <div id="feedback51" class="feedback"></div>
            </div>
            
            <!-- Question 52 -->
            <div class="question-container">
                <span class="question-number">Question 2/10</span>
                <p class="question-text">Bien que partageant le principe commun de protection de la dignité, le harcèlement moral et le harcèlement sexuel présentent des régimes juridiques distincts. Quelle différence substantielle justifie leur traitement séparé dans les collectivités territoriales ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q52" value="a" id="q52a">
                        <label for="q52a">Seul le harcèlement sexuel nécessite un lien hiérarchique entre auteur et victime</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q52" value="b" id="q52b">
                        <label for="q52b">Le harcèlement moral exige systématiquement la répétition des agissements, tandis que le harcèlement sexuel peut être caractérisé par un acte unique en cas de "pression grave"</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q52" value="c" id="q52c">
                        <label for="q52c">Le harcèlement sexuel est toujours plus grave et entraîne automatiquement des sanctions disciplinaires plus sévères</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q52" value="d" id="q52d">
                        <label for="q52d">Seul le harcèlement moral requiert la démonstration d'une dégradation effective des conditions de travail</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q52', 'b', 'La distinction fondamentale réside dans l\'exigence de répétition : indispensable pour le harcèlement moral, elle peut être absente pour le harcèlement sexuel lorsqu\'il s\'agit d\'une pression grave exercée dans le but réel ou apparent d\'obtenir un acte de nature sexuelle. Cette différence influence les stratégies probatoires et les procédures d\'enquête.')">✓ Valider cette réponse</button>
                <div id="feedback52" class="feedback"></div>
            </div>
            
            <!-- Question 53 -->
            <div class="question-container">
                <span class="question-number">Question 3/10</span>
                <p class="question-text">Dans le cadre du harcèlement moral, la notion de "dégradation des conditions de travail" est centrale. Comment la jurisprudence administrative interprète-t-elle généralement cette notion ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q53" value="a" id="q53a">
                        <label for="q53a">Elle exige systématiquement une modification contractuelle ou organisationnelle formelle du poste de travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q53" value="b" id="q53b">
                        <label for="q53b">Elle s'apprécie de manière objective mais peut inclure des atteintes à l'environnement relationnel ou psychologique du travail, sans nécessiter de changement matériel tangible</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q53" value="c" id="q53c">
                        <label for="q53c">Elle nécessite la production d'un certificat médical attestant d'une incapacité de travail</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q53" value="d" id="q53d">
                        <label for="q53d">Elle est présumée dès lors que l'agent formule des plaintes répétées, sans qu'une enquête approfondie soit nécessaire</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q53', 'b', 'La jurisprudence administrative adopte une conception large et objective de la dégradation des conditions de travail. Elle peut inclure non seulement des modifications matérielles, mais aussi des atteintes à l\'environnement relationnel (isolement, mise à l\'écart), des pratiques managériales abusives, ou la privation de sens du travail. L\'essentiel est que cette dégradation soit susceptible de porter atteinte aux droits, à la dignité, ou à la santé de l\'agent.')">✓ Valider cette réponse</button>
                <div id="feedback53" class="feedback"></div>
            </div>
            
            <!-- Question 54 -->
            <div class="question-container">
                <span class="question-number">Question 4/10</span>
                <p class="question-text">L'article L. 131-3 du CGFP introduit la notion d'"agissement sexiste". En quoi cette qualification juridique se distingue-t-elle conceptuellement du harcèlement sexuel, et quel est son intérêt dans la stratégie de prévention ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q54" value="a" id="q54a">
                        <label for="q54a">L'agissement sexiste constitue une forme atténuée de harcèlement sexuel, relevant d'une procédure disciplinaire simplifiée</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q54" value="b" id="q54b">
                        <label for="q54b">L'agissement sexiste concerne exclusivement les remarques sexistes entre collègues de même niveau hiérarchique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q54" value="c" id="q54c">
                        <label for="q54c">Il s'agit d'un concept plus large qui vise à prévenir les comportements hostiles ou dégradants liés au sexe, avant qu'ils n'évoluent vers du harcèlement sexuel caractérisé, permettant ainsi une intervention précoce</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q54" value="d" id="q54d">
                        <label for="q54d">Cette notion est purement déclarative et n'engage pas la responsabilité de l'employeur public</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q54', 'c', 'L\'agissement sexiste est un concept distinct et complémentaire du harcèlement sexuel. Il permet de sanctionner des comportements qui, sans nécessairement atteindre le seuil du harcèlement, contribuent à créer un environnement de travail hostile ou dégradant en raison du sexe. Cette notion offre un outil de prévention précoce et participe à une approche globale de lutte contre les violences sexistes et sexuelles.')">✓ Valider cette réponse</button>
                <div id="feedback54" class="feedback"></div>
            </div>
            
            <!-- Question 55 -->
            <div class="question-container">
                <span class="question-number">Question 5/10</span>
                <p class="question-text">Concernant l'élément moral (intention) du harcèlement, comment le droit administratif concilie-t-il la nécessité de prouver une intention avec la protection des victimes ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q55" value="a" id="q55a">
                        <label for="q55a">L'intention explicite de nuire doit être établie avec certitude, ce qui rend la qualification juridique particulièrement difficile</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q55" value="b" id="q55b">
                        <label for="q55b">Pour le harcèlement moral, l'élément intentionnel est présumé dès lors que les agissements répétés sont établis, se focalisant sur leurs effets objectifs plutôt que sur les intentions subjectives de l'auteur</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q55" value="c" id="q55c">
                        <label for="q55c">L'élément moral est totalement indifférent, seuls les effets matériels des agissements étant pris en compte</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q55" value="d" id="q55d">
                        <label for="q55d">L'intention doit être établie par des preuves directes (écrits, enregistrements) excluant ainsi les preuves par présomption</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q55', 'b', 'Le droit administratif adopte une approche pragmatique : pour le harcèlement moral, il suffit que les agissements répétés aient pour objet ou pour effet de dégrader les conditions de travail. Cette formulation permet de retenir la qualification même en l\'absence d\'intention explicite de nuire, en se concentrant sur les conséquences objectives des comportements. L\'élément moral se déduit ainsi des circonstances et des effets des agissements.')">✓ Valider cette réponse</button>
                <div id="feedback55" class="feedback"></div>
            </div>
            
            <!-- Question 56 -->
            <div class="question-container">
                <span class="question-number">Question 6/10</span>
                <p class="question-text">La loi n° 2008-496 du 27 mai 2008 a intégré le harcèlement dans le champ des discriminations. Quelles sont les implications concrètes de cette qualification en termes de procédure et de charge de la preuve ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q56" value="a" id="q56a">
                        <label for="q56a">Elle inverse partiellement la charge de la preuve : la victime présente des éléments laissant présumer une discrimination/harcèlement, et c'est à l'administration de démontrer l'absence de faits ou leur justification objective</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q56" value="b" id="q56b">
                        <label for="q56b">Elle impose systématiquement la saisine du Défenseur des droits comme préalable à toute action contentieuse</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q56" value="c" id="q56c">
                        <label for="q56c">Elle élimine toute possibilité de recours administratif préalable, obligeant à saisir directement le juge judiciaire</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q56" value="d" id="q56d">
                        <label for="q56d">Elle limite les sanctions possibles aux seules mesures disciplinaires, excluant les dommages-intérêts</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q56', 'a', 'L\'intégration du harcèlement dans le champ des discriminations a pour principale conséquence un aménagement probatoire favorable à la victime. Conformément à l\'article 9 du code de procédure civile, la victime doit présumer des faits de harcèlement/discrimination, puis c\'est à l\'auteur ou à l\'employeur de prouver que ces mesures étaient justifiées par des éléments objectifs étrangers à toute discrimination. Ce renversement partiel de la charge de la preuve constitue une avancée majeure pour la protection des victimes.')">✓ Valider cette réponse</button>
                <div id="feedback56" class="feedback"></div>
            </div>
            
            <!-- Question 57 -->
            <div class="question-container">
                <span class="question-number">Question 7/10</span>
                <p class="question-text">Dans la caractérisation du harcèlement sexuel, comment le droit administratif distingue-t-il la "simple séduction" (non répréhensible) du harcèlement sexuel ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q57" value="a" id="q57a">
                        <label for="q57a">La séduction est toujours licite lorsqu'elle émane de collègues de même niveau hiérarchique</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q57" value="b" id="q57b">
                        <label for="q57b">La distinction réside dans le caractère réciproque et respectueux de la séduction, et dans son absence de perturbation du fonctionnement du service, contrairement au harcèlement qui implique une imposition non désirée et crée un environnement hostile</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q57" value="c" id="q57c">
                        <label for="q57c">Toute démarche de séduction dans le cadre professionnel est automatiquement qualifiée de harcèlement sexuel</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q57" value="d" id="q57d">
                        <label for="q57d">La séduction n'est jamais problématique lorsqu'elle reste verbale, sans contact physique</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q57', 'b', 'La distinction fondamentale réside dans le consentement et les effets sur l\'environnement de travail. La séduction suppose une réciprocité et le respect de la liberté de l\'autre. Elle devient problématique (et peut basculer vers le harcèlement) lorsqu\'elle est ambiguë, abusive, incompatible avec un lien hiérarchique, ou qu\'elle perturbe le fonctionnement du service en créant une situation intimidante, hostile ou offensante pour la personne visée.')">✓ Valider cette réponse</button>
                <div id="feedback57" class="feedback"></div>
            </div>
            
            <!-- Question 58 -->
            <div class="question-container">
                <span class="question-number">Question 8/10</span>
                <p class="question-text">Les "manifestations spécifiques" du harcèlement moral évoquées dans la doctrine (isolement, contrôle excessif, imposition d'objectifs irréalisables, etc.). Comment ces techniques s'inscrivent-elles dans la logique de qualification juridique ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q58" value="a" id="q58a">
                        <label for="q58a">Elles constituent une liste exhaustive et fermée de comportements prohibés</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q58" value="b" id="q58b">
                        <label for="q58b">Elles illustrent la diversité des modalités possibles du harcèlement moral mais ne dispensent pas de démontrer les trois critères cumulatifs (répétition, dégradation conditions de travail, dommage potentiel)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q58" value="c" id="q58c">
                        <label for="q58c">Elles permettent de qualifier automatiquement le harcèlement moral dès lors qu'une de ces techniques est identifiée</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q58" value="d" id="q58d">
                        <label for="q58d">Elles concernent exclusivement le harcèlement moral "vertical" (du supérieur vers le subordonné)</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q58', 'b', 'Ces manifestations illustrent la variété des stratégies de harcèlement mais n\'ont pas de valeur normative autonome. Elles aident à identifier et caractériser les agissements, mais la qualification juridique exige toujours la démonstration des trois éléments cumulatifs : 1) agissements répétés, 2) dégradation objective des conditions de travail, 3) caractère dommageable potentiel. Ces techniques sont des indices, non des conditions suffisantes.')">✓ Valider cette réponse</button>
                <div id="feedback58" class="feedback"></div>
            </div>
            
            <!-- Question 59 -->
            <div class="question-container">
                <span class="question-number">Question 9/10</span>
                <p class="question-text">Le harcèlement moral peut être exercé "individuellement ou collectivement" et "sans qu'un lien hiérarchique soit exigé". Quelles implications cette extension du champ des auteurs potentiels a-t-elle sur la responsabilité de l'employeur public ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q59" value="a" id="q59a">
                        <label for="q59a">Elle limite la responsabilité de l'employeur aux seuls cas impliquant des supérieurs hiérarchiques</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q59" value="b" id="q59b">
                        <label for="q59b">Elle renforce l'obligation de prévention de l'employeur, qui doit mettre en place des dispositifs efficaces contre toutes les formes de harcèlement, y compris horizontal ou collectif, et intervenir dès qu'il a connaissance de faits, quelle que soit la position des auteurs</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q59" value="c" id="q59c">
                        <label for="q59c">Elle rend la qualification plus difficile car nécessite d'identifier formellement chaque auteur individuel</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q59" value="d" id="q59d">
                        <label for="q59d">Elle exclut la possibilité de sanctions disciplinaires pour les auteurs non hiérarchiques</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q59', 'b', 'Cette extension élargit considérablement le champ de la responsabilité de l\'employeur public. Elle signifie que l\'obligation de prévention et de réaction ne se limite pas aux relations hiérarchiques mais couvre l\'ensemble des relations professionnelles. L\'employeur doit donc mettre en place une politique globale de prévention, former tous les agents, et intervenir efficacement quel que soit le statut des auteurs (collègues, subordonnés, élus, etc.). Cette approche correspond à l\'obligation générale de sécurité qui incombe à l\'employeur public.')">✓ Valider cette réponse</button>
                <div id="feedback59" class="feedback"></div>
            </div>
            
            <!-- Question 60 -->
            <div class="question-container">
                <span class="question-number">Question 10/10</span>
                <p class="question-text">La distinction entre "objet" et "effet" dans la définition du harcèlement ("ayant pour objet ou pour effet...") a une importance juridique majeure. Comment cette disjonctive influence-t-elle la qualification des faits ?</p>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q60" value="a" id="q60a">
                        <label for="q60a">Elle crée deux infractions distinctes avec des régimes probatoires différents</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q60" value="b" id="q60b">
                        <label for="q60b">Elle permet de retenir la qualification même lorsque l'auteur n'avait pas l'intention de nuire, pourvu que les agissements aient produit ou soient susceptibles de produire les effets dommageables visés par la loi</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q60" value="c" id="q60c">
                        <label for="q60c">Elle limite la responsabilité aux seuls cas où l'intention de nuire est clairement établie ("objet")</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q60" value="d" id="q60d">
                        <label for="q60d">Elle établit une hiérarchie entre le harcèlement intentionnel (plus grave) et le harcèlement par effet (moins grave)</label>
                    </div>
                </div>
                <button class="validate-btn" onclick="checkAnswer('q60', 'b', 'Cette distinction objet ou effet est une clé de voûte du régime juridique du harcèlement. Elle permet de sanctionner non seulement les comportements délibérément hostiles, mais aussi ceux qui, sans intention malveillante, produisent objectivement des effets dommageables (dégradation des conditions de travail, atteinte à la santé, etc.). Cette approche objective protège mieux les victimes en se focalisant sur les conséquences réelles des agissements plutôt que sur les intentions subjectives de l\'auteur.')">✓ Valider cette réponse</button>
                <div id="feedback60" class="feedback"></div>
            </div>
        </div>

        <!-- Score -->
        <div class="score-container">
            <div class="score-label">Votre score actuel</div>
            <div class="score-value" id="score">0</div>
            <div class="score-total">sur 60 points possibles</div>
        </div>

        <!-- Bouton diplôme -->
        <button class="diploma-btn" onclick="showCertificate()">
            🏆 Obtenir mon diplôme de qualification
        </button>

        <!-- Diplôme (contenu inchangé) -->
        <div id="certificate-container" class="certificate-container">
            <div class="certificate-diploma">
                <div class="certificate-header">
                    <div class="certificate-title">Diplôme de Qualification Professionnelle</div>
                    <div class="certificate-subtitle">Formation en prévention du harcèlement</div>
                    <div style="font-size: 14px; color: #777; margin-top: 5px;">Collectivités Territoriales</div>
                </div>
                
                <div class="certificate-body">
                    <div class="certificate-awarded">Décerné à :</div>
                    <div class="certificate-name" id="diploma-name">[Nom du participant]</div>
                    
                    <div class="certificate-achievement">
                        En reconnaissance de la réussite au programme de formation sur
                        <div class="certificate-course">
                            "Protection des agents victimes de harcèlement dans les collectivités territoriales"
                        </div>
                        
                        <div class="certificate-score" id="diploma-score">
                            Score obtenu : <span id="diploma-score-value">0</span>/60 (<span id="diploma-percentage">0</span>%)
                        </div>
                    </div>
                    
                    <div class="certificate-details">
                        <p><strong>Compétences validées :</strong></p>
                        <ul style="margin: 10px 0 0 20px; padding: 0;">
                            <li>Cadre légal et obligations des employeurs publics</li>
                            <li>Dispositifs de signalement et procédures</li>
                            <li>Conduite d'enquêtes administratives</li>
                            <li>Protection fonctionnelle des agents</li>
                            <li>Sanctions disciplinaires et recours juridiques</li>
                            <li>Caractérisation juridique du harcèlement</li>
                        </ul>
                    </div>
                    
                    <div class="result-message" id="diploma-message">
                        <!-- Message personnalisé inséré ici -->
                    </div>
                </div>
                
                <div class="certificate-footer">
                    <div class="signature-box">
                        <div class="signature-line"></div>
                        <div class="signature-title">Directeur de la Formation</div>
                    </div>
                    
                    <div style="text-align: center; flex: 1;">
                        <div>Délivré le <span id="diploma-date"></span></div>
                        <div style="font-size: 12px; color: #777; margin-top: 5px;">ID: <span id="diploma-id"></span></div>
                    </div>
                    
                    <div class="signature-box">
                        <div class="signature-line"></div>
                        <div class="signature-title">Référent Harcèlement</div>
                    </div>
                </div>
                
                <div class="certificate-seal">
                    <div>VÉRIFIÉ<br>ET<br>APPROUVÉ</div>
                </div>
                
                <div class="certificate-id">
                    Certificat électronique • Non falsifiable
                </div>
            </div>
            
            <div class="certificate-actions">
                <button class="download-diploma-btn" onclick="downloadDiploma()">📥 Télécharger le diplôme</button>
                <button class="print-diploma-btn" onclick="printDiploma()">🖨️ Imprimer le diplôme</button>
            </div>
        </div>
    </div>

    <script>
        let score = 0;
        let totalQuestions = 60;
        let answeredQuestions = 0;

        function showTheme(themeId) {
            document.querySelectorAll('.theme').forEach(theme => {
                theme.classList.remove('active');
            });
            document.getElementById(themeId).classList.add('active');
            updateProgress();
        }

        function checkAnswer(questionId, correctAnswer, explanation) {
            const selectedOption = document.querySelector(`input[name="${questionId}"]:checked`);
            const questionNumber = questionId.substring(1);
            const feedbackElement = document.getElementById(`feedback${questionNumber}`);

            if (selectedOption) {
                answeredQuestions++;
                if (selectedOption.value === correctAnswer) {
                    feedbackElement.textContent = "✅ Bonne réponse ! " + explanation;
                    feedbackElement.className = "feedback correct";
                    score++;
                } else {
                    feedbackElement.textContent = "❌ Mauvaise réponse. " + explanation;
                    feedbackElement.className = "feedback incorrect";
                }
                feedbackElement.style.display = "block";
                document.getElementById("score").textContent = score;
                updateProgress();
            } else {
                alert("Veuillez sélectionner une réponse avant de valider.");
            }
        }

        function updateProgress() {
            const progress = Math.min(100, Math.round((answeredQuestions / totalQuestions) * 100));
            document.getElementById('progress-fill').style.width = progress + '%';
            document.getElementById('progress-percent').textContent = progress + '%';
        }

        // Fonctions pour le diplôme (inchangées)
        function showCertificate() {
            const certificateContainer = document.getElementById('certificate-container');
            const percentage = Math.round((score / totalQuestions) * 100);
            const resultMessage = document.getElementById('diploma-message');
            
            const userName = prompt("Veuillez entrer votre nom pour le diplôme:", "Nom Prénom");
            
            if (!userName) {
                return;
            }
            
            document.getElementById('diploma-name').textContent = userName;
            document.getElementById('diploma-score-value').textContent = score;
            document.getElementById('diploma-percentage').textContent = percentage;
            
            const today = new Date();
            const options = { year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('diploma-date').textContent = today.toLocaleDateString('fr-FR', options);
            
            const diplomaId = 'DPL-' + today.getFullYear() + '-' + 
                            String(today.getMonth() + 1).padStart(2, '0') + '-' + 
                            String(today.getDate()).padStart(2, '0') + '-' + 
                            Math.floor(Math.random() * 10000).toString().padStart(4, '0');
            document.getElementById('diploma-id').textContent = diplomaId;
            
            let message = '';
            let messageClass = '';
            
            if (percentage >= 90) {
                messageClass = 'excellent-message';
                message = `<p style="font-weight: bold; color: #27ae60; margin-bottom: 10px;">🎉 Niveau d'excellence atteint !</p>
                          <p>Félicitations pour cette performance exceptionnelle ! Vous démontrez une maîtrise complète des dispositifs de protection contre le harcèlement.</p>`;
            }
            else if (percentage >= 75) {
                messageClass = 'good-message';
                message = `<p style="font-weight: bold; color: #f39c12; margin-bottom: 10px;">👏 Niveau avancé validé !</p>
                          <p>Excellent travail ! Vous avez une compréhension approfondie des mécanismes de protection et des obligations légales.</p>`;
            }
            else if (percentage >= 60) {
                messageClass = 'good-message';
                message = `<p style="font-weight: bold; color: #3498db; margin-bottom: 10px;">📚 Niveau intermédiaire atteint</p>
                          <p>Bonne performance ! Vous maîtrisez les principes fondamentaux de la protection contre le harcèlement.</p>`;
            }
            else if (percentage >= 40) {
                messageClass = 'average-message';
                message = `<p style="font-weight: bold; color: #e74c3c; margin-bottom: 10px;">⚠️ Niveau de base validé</p>
                          <p>Vous avez acquis les connaissances de base sur le sujet. Une formation complémentaire est recommandée pour approfondir votre expertise.</p>`;
            }
            else {
                messageClass = 'average-message';
                message = `<p style="font-weight: bold; color: #c0392b; margin-bottom: 10px;">📝 Participation reconnue</p>
                          <p>Merci pour votre participation. Ce diplôme atteste de votre engagement dans la formation sur la prévention du harcèlement.</p>`;
            }
            
            resultMessage.innerHTML = message;
            resultMessage.className = 'result-message ' + messageClass;
            
            certificateContainer.classList.add('active');
            certificateContainer.scrollIntoView({ behavior: 'smooth' });
        }

        function downloadDiploma() {
            const diplomaElement = document.querySelector('.certificate-diploma');
            const userName = document.getElementById('diploma-name').textContent;
            
            if (userName === '[Nom du participant]') {
                alert("Veuillez d'abord générer votre diplôme en cliquant sur 'Obtenir mon diplôme'");
                return;
            }
            
            const diplomaContent = `
                <!DOCTYPE html>
                <html>
                <head>
                    <meta charset="UTF-8">
                    <title>Diplôme - Protection contre le harcèlement</title>
                    <style>
                        body {
                            font-family: 'Georgia', 'Times New Roman', serif;
                            margin: 0;
                            padding: 40px;
                            background: linear-gradient(to bottom right, #fdf6e3, #fffef6);
                            color: #2c3e50;
                        }
                        .certificate-diploma {
                            background: white;
                            border: 15px solid;
                            border-image: linear-gradient(45deg, #d4af37, #ffd700, #d4af37) 1;
                            padding: 40px;
                            text-align: center;
                            max-width: 800px;
                            margin: 0 auto;
                            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
                        }
                        .certificate-title {
                            font-size: 28px;
                            font-weight: bold;
                            color: #2c3e50;
                            letter-spacing: 2px;
                            margin-bottom: 10px;
                            text-transform: uppercase;
                        }
                        .certificate-name {
                            font-size: 32px;
                            font-weight: bold;
                            color: #2c3e50;
                            margin: 20px 0;
                            padding: 10px;
                            border-top: 2px solid #d4af37;
                            border-bottom: 2px solid #d4af37;
                            display: inline-block;
                        }
                        .certificate-score {
                            font-size: 24px;
                            font-weight: bold;
                            color: #27ae60;
                            margin: 15px 0;
                        }
                        .certificate-footer {
                            margin-top: 40px;
                            padding-top: 20px;
                            border-top: 1px solid #ddd;
                            display: flex;
                            justify-content: space-between;
                        }
                        .signature-line {
                            border-top: 1px solid #000;
                            width: 200px;
                            margin: 40px auto 10px;
                        }
                        @media print {
                            @page {
                                size: A4 landscape;
                                margin: 0;
                            }
                            body {
                                padding: 0;
                            }
                        }
                    </style>
                </head>
                <body>
                    ${diplomaElement.outerHTML}
                </body>
                </html>
            `;
            
            const blob = new Blob([diplomaContent], { type: 'text/html' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = `Diplome_Harcelement_${userName.replace(/\s+/g, '_')}.html`;
            link.click();
        }

        function printDiploma() {
            const userName = document.getElementById('diploma-name').textContent;
            
            if (userName === '[Nom du participant]') {
                alert("Veuillez d'abord générer votre diplôme en cliquant sur 'Obtenir mon diplôme'");
                return;
            }
            
            window.print();
        }

        updateProgress();
    </script>
</body>
</html>
