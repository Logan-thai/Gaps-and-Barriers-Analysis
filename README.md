<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gaps and Barriers Analysis Template</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 20px;
            background-color: #f8f9fa;
            color: #333;
        }
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .header {
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 3px solid #0094D7;
            padding-bottom: 20px;
        }
        .header h1 {
            color: #0094D7;
            margin: 0;
            font-size: 28px;
        }
        .project-info {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #E8F4F8 0%, #F0F8FB 100%);
            padding: 20px;
            border-radius: 6px;
            border: 1px solid #B3E5FC;
        }
        .info-field {
            display: flex;
            flex-direction: column;
        }
        .info-field label {
            font-weight: bold;
            color: #1976D2;
            margin-bottom: 5px;
        }
        .info-field input {
            padding: 8px;
            border: 1px solid #81C784;
            border-radius: 4px;
            font-size: 14px;
            transition: border-color 0.3s ease;
        }
        .info-field input:focus {
            outline: none;
            border-color: #0094D7;
        }
        .analysis-section {
            margin-bottom: 30px;
        }
        .section-title {
            background: linear-gradient(135deg, #0094D7 0%, #1976D2 100%);
            color: white;
            padding: 12px 20px;
            margin: 0 0 20px 0;
            border-radius: 6px;
            font-size: 18px;
            font-weight: bold;
        }
        .states-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }
        .state-box {
            border: 2px solid #B3E5FC;
            border-radius: 6px;
            padding: 20px;
            background: linear-gradient(135deg, #F8FDFF 0%, #E8F4F8 100%);
        }
        .state-box.current {
            border-color: #003359;
            background: linear-gradient(135deg, #E3F2FD 0%, #BBDEFB 100%);
        }
        .state-box.desired {
            border-color: #0094D7;
            background: linear-gradient(135deg, #E1F5FE 0%, #81D4FA 100%);
        }
        .state-title {
            font-weight: bold;
            margin-bottom: 10px;
            font-size: 16px;
        }
        .state-box.current .state-title {
            color: #003359;
        }
        .state-box.desired .state-title {
            color: #0094D7;
        }
        .state-content {
            min-height: 100px;
            padding: 10px;
            border: 1px solid #B3E5FC;
            border-radius: 4px;
            background: white;
            font-size: 14px;
        }
        .gaps-barriers-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }
        .analysis-box {
            border: 2px solid #B3E5FC;
            border-radius: 6px;
            padding: 20px;
            background: linear-gradient(135deg, #F8FDFF 0%, #E8F4F8 100%);
        }
        .analysis-box.gaps {
            border-color: #4FC3F7;
            background: linear-gradient(135deg, #E1F5FE 0%, #B3E5FC 100%);
        }
        .analysis-box.barriers {
            border-color: #29B6F6;
            background: linear-gradient(135deg, #E3F2FD 0%, #90CAF9 100%);
        }
        .analysis-title {
            font-weight: bold;
            margin-bottom: 15px;
            font-size: 16px;
        }
        .analysis-box.gaps .analysis-title {
            color: #0288D1;
        }
        .analysis-box.barriers .analysis-title {
            color: #0277BD;
        }
        .analysis-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        .analysis-item {
            background: white;
            border: 1px solid #B3E5FC;
            border-radius: 4px;
            padding: 12px;
            margin-bottom: 10px;
            min-height: 30px;
            font-size: 14px;
        }
        .action-plan {
            background: linear-gradient(135deg, #E8F4F8 0%, #B3E5FC 100%);
            border: 2px solid #42A5F5;
            border-radius: 6px;
            padding: 20px;
        }
        .action-title {
            color: #1976D2;
            font-weight: bold;
            margin-bottom: 15px;
            font-size: 16px;
        }
        .action-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 4px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .action-table th {
            background: linear-gradient(135deg, #0094D7 0%, #1976D2 100%);
            color: white;
            padding: 12px;
            text-align: left;
            font-weight: bold;
        }
        .action-table td {
            padding: 12px;
            border-bottom: 1px solid #E3F2FD;
            vertical-align: top;
        }
        .action-table tr:last-child td {
            border-bottom: none;
        }
        .priority-high { 
            background: linear-gradient(135deg, #BBDEFB 0%, #90CAF9 100%);
            border-left: 4px solid #1976D2;
        }
        .priority-medium { 
            background: linear-gradient(135deg, #E3F2FD 0%, #BBDEFB 100%);
            border-left: 4px solid #42A5F5;
        }
        .priority-low { 
            background: linear-gradient(135deg, #F3F9FF 0%, #E8F4F8 100%);
            border-left: 4px solid #81D4FA;
        }
        .instructions {
            background: linear-gradient(135deg, #E3F2FD 0%, #BBDEFB 100%);
            border: 1px solid #42A5F5;
            border-radius: 6px;
            padding: 15px;
            margin-bottom: 20px;
            font-size: 14px;
        }
        .instructions strong {
            color: #0D47A1;
        }
        @media (max-width: 768px) {
            .states-container,
            .gaps-barriers-container {
                grid-template-columns: 1fr;
            }
            .project-info {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Gaps and Barriers Analysis</h1>
        </div>
        
        <div class="instructions">
            <strong>Instructions:</strong> Use this template to identify the gap between your current state and desired state, then analyze what barriers are preventing progress and what actions are needed to overcome them.
        </div>

        <div class="project-info">
            <div class="info-field">
                <label>Project/Process Name:</label>
                <input type="text" placeholder="Enter project or process name">
            </div>
            <div class="info-field">
                <label>Date:</label>
                <input type="date">
            </div>
            <div class="info-field">
                <label>Team Lead:</label>
                <input type="text" placeholder="Enter team lead name">
            </div>
            <div class="info-field">
                <label>Department:</label>
                <input type="text" placeholder="Enter department">
            </div>
        </div>

        <div class="analysis-section">
            <h2 class="section-title">Step 1: Define Current and Desired States</h2>
            <div class="states-container">
                <div class="state-box current">
                    <div class="state-title">Current State (Where We Are Now)</div>
                    <div class="state-content" contenteditable="true">
                        Click here to describe the current situation, including key metrics, performance levels, and specific issues...
                    </div>
                </div>
                <div class="state-box desired">
                    <div class="state-title">Desired State (Where We Want to Be)</div>
                    <div class="state-content" contenteditable="true">
                        Click here to describe the target situation, including specific goals, metrics, and success criteria...
                    </div>
                </div>
            </div>
        </div>

        <div class="analysis-section">
            <h2 class="section-title">Step 2: Identify Gaps and Barriers</h2>
            <div class="gaps-barriers-container">
                <div class="analysis-box gaps">
                    <div class="analysis-title">Gaps (What's Missing)</div>
                    <ul class="analysis-list">
                        <li class="analysis-item" contenteditable="true">Click to add gap #1...</li>
                        <li class="analysis-item" contenteditable="true">Click to add gap #2...</li>
                        <li class="analysis-item" contenteditable="true">Click to add gap #3...</li>
                        <li class="analysis-item" contenteditable="true">Click to add gap #4...</li>
                        <li class="analysis-item" contenteditable="true">Click to add gap #5...</li>
                    </ul>
                </div>
                <div class="analysis-box barriers">
                    <div class="analysis-title">Barriers (What's Blocking Progress)</div>
                    <ul class="analysis-list">
                        <li class="analysis-item" contenteditable="true">Click to add barrier #1...</li>
                        <li class="analysis-item" contenteditable="true">Click to add barrier #2...</li>
                        <li class="analysis-item" contenteditable="true">Click to add barrier #3...</li>
                        <li class="analysis-item" contenteditable="true">Click to add barrier #4...</li>
                        <li class="analysis-item" contenteditable="true">Click to add barrier #5...</li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="analysis-section">
            <h2 class="section-title">Step 3: Action Plan</h2>
            <div class="action-plan">
                <div class="action-title">Actions to Close Gaps and Overcome Barriers</div>
                <table class="action-table">
                    <thead>
                        <tr>
                            <th>Action Required</th>
                            <th>Owner</th>
                            <th>Target Date</th>
                            <th>Priority</th>
                            <th>Success Measure</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="priority-high">
                            <td contenteditable="true">Click to add action #1...</td>
                            <td contenteditable="true">Name</td>
                            <td contenteditable="true">MM/DD/YYYY</td>
                            <td>High</td>
                            <td contenteditable="true">How will we know it's complete?</td>
                        </tr>
                        <tr class="priority-medium">
                            <td contenteditable="true">Click to add action #2...</td>
                            <td contenteditable="true">Name</td>
                            <td contenteditable="true">MM/DD/YYYY</td>
                            <td>Medium</td>
                            <td contenteditable="true">How will we know it's complete?</td>
                        </tr>
                        <tr class="priority-medium">
                            <td contenteditable="true">Click to add action #3...</td>
                            <td contenteditable="true">Name</td>
                            <td contenteditable="true">MM/DD/YYYY</td>
                            <td>Medium</td>
                            <td contenteditable="true">How will we know it's complete?</td>
                        </tr>
                        <tr class="priority-low">
                            <td contenteditable="true">Click to add action #4...</td>
                            <td contenteditable="true">Name</td>
                            <td contenteditable="true">MM/DD/YYYY</td>
                            <td>Low</td>
                            <td contenteditable="true">How will we know it's complete?</td>
                        </tr>
                        <tr class="priority-low">
                            <td contenteditable="true">Click to add action #5...</td>
                            <td contenteditable="true">Name</td>
                            <td contenteditable="true">MM/DD/YYYY</td>
                            <td>Low</td>
                            <td contenteditable="true">How will we know it's complete?</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
