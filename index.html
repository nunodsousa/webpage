<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Theory: Prisoner's Dilemma</title>
    <style>
        /* Basic styling for readability */
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            margin: 2em;
            background-color: #f4f4f4;
            color: #333;
            line-height: 1.6;
        }
        .container {
            max-width: 700px;
            margin: 0 auto;
            padding: 25px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }
        h1, h2 {
            color: #2c3e50;
            border-bottom: 2px solid #ecf0f1;
            padding-bottom: 10px;
        }
        .player-section {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            font-size: 1rem;
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            background-color: #3498db;
            color: white;
            transition: background-color 0.2s;
        }
        button:hover {
            background-color: #2980b9;
        }
        button.selected {
            background-color: #2ecc71;
            font-weight: bold;
            box-shadow: 0 0 5px rgba(46, 204, 113, 0.7);
        }
        button:disabled {
            background-color: #bdc3c7;
            cursor: not-allowed;
        }
        #resolve_game {
            background-color: #e74c3c;
        }
        #resolve_game:hover {
            background-color: #c0392b;
        }
        #reset_game {
            background-color: #95a5a6;
        }
        #reset_game:hover {
            background-color: #7f8c8d;
        }
        #result {
            margin-top: 20px;
            padding: 15px;
            background-color: #ecf0f1;
            border-radius: 5px;
            font-size: 1.1rem;
            border-left: 5px solid #3498db;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Game Theory: Prisoner's Dilemma</h1>
        <p>Two prisoners, unable to communicate, must decide whether to <strong>Cooperate</strong> (stay silent) or <strong>Defect</strong> (betray). Outcomes are measured in years of prison sentence (a lower negative score is better).</p>
        
        <h3>Payoff Matrix (Player 1, Player 2)</h3>
        <table>
            <tr>
                <th></th>
                <th>P2 Cooperate</th>
                <th>P2 Defect</th>
            </tr>
            <tr>
                <td><strong>P1 Cooperate</strong></td>
                <td>(-1, -1)</td>
                <td>(-3, 0)</td>
            </tr>
            <tr>
                <td><strong>P1 Defect</strong></td>
                <td>(0, -3)</td>
                <td>(-2, -2)</td>
            </tr>
        </table>

        <div class="player-section" id="p1_section">
            <h2>Player 1's Choice</h2>
            <button class="choice" data-player="1" data-choice="cooperate">Cooperate</button>
            <button class="choice" data-player="1" data-choice="defect">Defect</button>
        </div>
        
        <div class="player-section" id="p2_section">
            <h2>Player 2's Choice</h2>
            <button class="choice" data-player="2" data-choice="cooperate">Cooperate</button>
            <button class="choice" data-player="2" data-choice="defect">Defect</button>
        </div>
        
        <hr>
        
        <button id="resolve_game">Resolve Outcome</button>
        <button id="reset_game">Reset</button>
        
        <div id="result">
            <p>Make your choices and click 'Resolve Outcome'.</p>
        </div>
    </div>

    <script>
        /**
         * Main application logic, encapsulated in a DOMContentLoaded event listener
         * to ensure the DOM is fully loaded before attaching handlers.
         */
        document.addEventListener('DOMContentLoaded', () => {
            
            // --- State ---
            let p1_choice = null;
            let p2_choice = null;

            /**
             * Payoff Matrix: payoff[p1_choice][p2_choice] -> [p1_score, p2_score]
             * Scores represent years in prison (negative numbers). 0 is best.
             */
            const payoff = {
                'cooperate': {
                    'cooperate': [-1, -1], // Both cooperate: 1 year each
                    'defect': [-3, 0]      // P1 cooperates, P2 defects: P1=3 years, P2=0 years
                },
                'defect': {
                    'cooperate': [0, -3],  // P1 defects, P2 cooperates: P1=0 years, P2=3 years
                    'defect': [-2, -2]     // Both defect: 2 years each
                }
            };

            // --- DOM Element Caching ---
            const p1_buttons = document.querySelectorAll('#p1_section .choice');
            const p2_buttons = document.querySelectorAll('#p2_section .choice');
            const all_buttons = document.querySelectorAll('.choice');
            const resolve_button = document.getElementById('resolve_game');
            const reset_button = document.getElementById('reset_game');
            const result_div = document.getElementById('result');

            // --- Event Handlers ---

            /**
             * Handles choice selection for a player.
             * @param {Event} e - The click event.
             */
            function selectChoice(e) {
                const choice = e.target.dataset.choice;
                const player_num = parseInt(e.target.dataset.player, 10);
                
                let button_group;
                
                if (player_num === 1) {
                    p1_choice = choice;
                    button_group = p1_buttons;
                } else {
                    p2_choice = choice;
                    button_group = p2_buttons;
                }
                
                // Visual feedback: Highlight selected, disable group
                button_group.forEach(btn => {
                    if (btn === e.target) {
                        btn.classList.add('selected');
                        btn.disabled = true; // Disable selected
                    } else {
                        btn.classList.remove('selected');
                        btn.disabled = true; // Disable other choice
                    }
                });
            }

            /**
             * Resolves the game based on current choices and displays the outcome.
             */
            function resolveGame() {
                if (!p1_choice || !p2_choice) {
                    result_div.innerHTML = `<p style="color: #e74c3c;">Both players must make a choice.</p>`;
                    return;
                }

                const [p1_score, p2_score] = payoff[p1_choice][p2_choice];

                let result_text = `
                    <p><strong>Player 1 chose:</strong> ${p1_choice}</p>
                    <p><strong>Player 2 chose:</strong> ${p2_choice}</p>
                    <hr>
                    <p><strong>Outcome:</strong></p>
                    <ul>
                        <li>Player 1 gets ${Math.abs(p1_score)} year(s).</li>
                        <li>Player 2 gets ${Math.abs(p2_score)} year(s).</li>
                    </ul>
                `;
                result_div.innerHTML = result_text;
                resolve_button.disabled = true;
            }

            /**
             * Resets the game to its initial state.
             */
            function resetGame() {
                p1_choice = null;
                p2_choice = null;
                
                all_buttons.forEach(btn => {
                    btn.classList.remove('selected');
                    btn.disabled = false;
                });
                
                resolve_button.disabled = false;
                result_div.innerHTML = `<p>Make your choices and click 'Resolve Outcome'.</p>`;
            }

            // --- Event Listeners Attachment ---
            all_buttons.forEach(button => {
                button.addEventListener('click', selectChoice);
            });

            resolve_button.addEventListener('click', resolveGame);
            reset_button.addEventListener('click', resetGame);

        });
    </script>

</body>
</html>
