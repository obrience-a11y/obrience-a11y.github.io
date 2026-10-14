<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Community Justice Alternatives Records Requests</title>
    <style>
        :root {
            --primary-color: #004B87;
            --secondary-color: #4A5568;
            --border-color: #CBD5E0;
            --bg-light: #F7FAFC;
            --accent-red: #C53030;
            --info-bg: #EBF8FF;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            line-height: 1.5;
            color: #2D3748;
            background-color: #EDF2F7;
            margin: 0;
            padding: 20px;
        }

        .form-container {
            max-width: 800px;
            margin: 0 auto;
            background: #FFFFFF;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .header {
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 15px;
            margin-bottom: 25px;
            text-align: center;
        }

        .header-logo-container {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 10px;
        }

        .header-logo-container img {
            max-height: 60px;
            width: auto;
        }

        .header h1 {
            color: var(--primary-color);
            font-size: 22px;
            margin: 0 0 5px 0;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .header .sub-header {
            font-size: 13px;
            color: var(--secondary-color);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group.required label::after {
            content: " *";
            color: var(--accent-red);
        }

        label {
            display: block;
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 14px;
        }

        .help-text {
            font-size: 12px;
            color: #718096;
            margin-top: 2px;
            margin-bottom: 6px;
        }

        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="date"],
        select,
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 14px;
        }

        input[type="file"] {
            display: block;
            margin-top: 6px;
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            margin-top: 10px;
        }

        .checkbox-group input[type="checkbox"] {
            margin-top: 3px;
        }

        .checkbox-group label {
            font-weight: normal;
            font-size: 14px;
        }

        .conditional-section {
            display: none;
            background-color: var(--bg-light);
            border-left: 4px solid var(--primary-color);
            padding: 15px;
            margin-top: 15px;
            border-radius: 0 4px 4px 0;
        }

        .info-box {
            background-color: var(--info-bg);
            border: 1px solid #BEE3F8;
            padding: 12px 15px;
            border-radius: 4px;
            font-size: 13px;
            color: #2B6CB0;
            margin-bottom: 20px;
        }

        .list-options {
            margin: 5px 0 10px 20px;
            padding: 0;
            font-size: 13px;
            color: #4A5568;
        }

        .row {
            display: flex;
            gap: 15px;
        }

        .row .form-group {
            flex: 1;
        }

        .footer-section {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
            font-size: 13px;
            color: var(--secondary-color);
        }

        .fee-schedule {
            background-color: #EDF2F7;
            padding: 15px;
            border-radius: 4px;
            margin-top: 15px;
            font-size: 12px;
            line-height: 1.6;
        }

        .submit-btn {
            background-color: var(--primary-color);
            color: white;
            padding: 12px 24px;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            margin-top: 20px;
        }

        .submit-btn:hover {
            background-color: #003366;
        }
    </style>
</head>
<body>

<div class="form-container">
    <!-- Header with Logo -->
    <div class="header">
        <div class="header-logo-container">
            <img src="larimer_county_logo.png" alt="Larimer County Community Justice Alternatives Logo" onerror="this.style.display='none'">
            <h1>Community Justice Alternatives Records Requests</h1>
        </div>
        <div class="sub-header">
            2307 Midpoint Drive, Fort Collins, Colorado 80525-4378 | 970.980.2600 | Larimer.gov/cja
        </div>
    </div>

    <form id="recordsRequestForm">
        <!-- Dropdown Question -->
        <div class="form-group required">
            <label for="requestorType">Type of Requester</label>
            <select id="requestorType" name="requestorType" required onchange="handleRequestorChange()">
                <option value="">-- Please Select --</option>
                <option value="client">I am a current or former client requesting my own criminal justice records</option>
                <option value="lawEnforcement">I work at a criminal justice or law enforcement agency or probation department</option>
                <option value="thirdParty">I am a third party (Public Defender, Attorney, Department of Human Services, etc)</option>
            </select>
        </div>

        <!-- Section 1 Main Form Container -->
        <div id="section1Main" style="display: none;">
            
            <!-- Requester Details -->
            <div class="row">
                <div class="form-group required">
                    <label id="requesterNameLabel" for="requesterName">Requester Name</label>
                    <input type="text" id="requesterName" name="requesterName" required oninput="updateIdentityConfirmationText()">
                </div>
                <div class="form-group required" id="agencyGroup">
                    <label for="agency">Agency</label>
                    <input type="text" id="agency" name="agency">
                </div>
                <div class="form-group required" id="titleGroup" style="display: none;">
                    <label for="titlePosition">Title or Position</label>
                    <input type="text" id="titlePosition" name="titlePosition">
                </div>
            </div>

            <div class="row">
                <div class="form-group required">
                    <label for="phone">Phone</label>
                    <input type="tel" id="phone" name="phone" required pattern="[0-9\-\+\(\)\s]+">
                </div>
                <div class="form-group required">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
            </div>

            <div class="form-group required">
                <label for="recordsRequested">Records Requested</label>
                <div class="help-text" id="recordsRequestedHelp"></div>
                <textarea id="recordsRequested" name="recordsRequested" rows="4" required></textarea>
            </div>

            <div class="form-group required">
                <label for="purposeOfRequest">Purpose of Request</label>
                <textarea id="purposeOfRequest" name="purposeOfRequest" rows="3" required></textarea>
            </div>

            <!-- Personal Gain Affirmation -->
            <div class="form-group required">
                <div class="checkbox-group">
                    <input type="checkbox" id="personalGainAffirmation" name="personalGainAffirmation" required>
                    <label for="personalGainAffirmation">
                        I affirm that I shall not use the requested records/information for direct solicitation of business for pecuniary gain. (per C.R.S. 24-72-305.5)
                    </label>
                </div>
            </div>

            <div class="row">
                <div class="form-group required">
                    <label for="requesterSignature">Requester's Signature</label>
                    <input type="text" id="requesterSignature" name="requesterSignature" placeholder="Type Full Name" required>
                </div>
                <div class="form-group required">
                    <label for="dateOfRequest">Date of Request</label>
                    <input type="date" id="dateOfRequest" name="dateOfRequest" required>
                </div>
                <div class="form-group required">
                    <label for="requestedDateToReceive">Requested Date to Receive Records</label>
                    <input type="date" id="requestedDateToReceive" name="requestedDateToReceive" required>
                </div>
            </div>

            <!-- LEO Specific Notice: Video Records -->
            <div id="leoVideoNotice" class="info-box" style="display: none;">
                If your request includes preservation of video records please contact our records team at <a href="mailto:cja-records@larimer.org">cja-records@larimer.org</a>.
            </div>

            <!-- Client Specific Section: Identity Verification -->
            <div id="clientUploadSection" class="conditional-section">
                <div class="form-group required">
                    <label for="clientVerificationDoc">Required Verification Document</label>
                    <div style="font-size: 13px; color: #4A5568;">Please upload one of:</div>
                    <ul class="list-options">
                        <li>A copy of a valid photo ID</li>
                        <li>A notarized copy of your signature and date</li>
                        <li>Your signature, date, and the signature of a Larimer County Staff witness</li>
                    </ul>
                    <input type="file" id="clientVerificationDoc" name="clientVerificationDoc">
                </div>

                <div class="form-group required">
                    <div class="checkbox-group">
                        <input type="checkbox" id="identityConfirmation" name="identityConfirmation">
                        <label for="identityConfirmation" id="identityConfirmationLabel">
                            I confirm I am [FullName] requesting my own records
                        </label>
                    </div>
                </div>
            </div>

            <!-- LEO Authorization Section (PHI) -->
            <div id="leoAuthSection" class="conditional-section">
                <div class="form-group">
                    <div class="checkbox-group">
                        <input type="checkbox" id="phiInclusion" name="phiInclusion" onchange="togglePhiFields()">
                        <label for="phiInclusion">My request includes protected health information</label>
                    </div>
                </div>

                <div id="phiFieldsContainer" style="display: none;">
                    <div class="form-group">
                        <label for="phiAuthorizationFile">PHI Authorization / Release Form</label>
                        <div class="help-text">Please include your current release of information or download this form and have the client sign it.</div>
                        <input type="file" id="phiAuthorizationFile" name="phiAuthorizationFile" onchange="handlePhiUploadChange()">
                    </div>

                    <div id="phiExplanationGroup" class="form-group required">
                        <label for="phiExplanation">Reason for Missing Authorization</label>
                        <div class="help-text">If you do not have a signed Release of Information or Authorization form, please explain why.</div>
                        <textarea id="phiExplanation" name="phiExplanation" rows="3"></textarea>
                    </div>
                </div>
            </div>

            <!-- Third Party Authorization Section -->
            <div id="thirdPartyAuthSection" class="conditional-section">
                <div class="form-group">
                    <label for="thirdPartyAuthFile">Authorization to Release Form</label>
                    <div class="help-text">Please attach the Authorization to Release form if available.</div>
                    <input type="file" id="thirdPartyAuthFile" name="thirdPartyAuthFile" onchange="handleThirdPartyUploadChange()">
                </div>

                <div id="thirdPartyExplanationGroup" class="form-group required">
                    <label for="thirdPartyExplanation">Reason for Missing Authorization</label>
                    <div class="help-text">If you do not have a signed Authorization to Release form, please explain why.</div>
                    <textarea id="thirdPartyExplanation" name="thirdPartyExplanation" rows="3"></textarea>
                </div>
            </div>

            <!-- Client Accommodation Notice -->
            <div id="clientAccommodationNotice" class="footer-section" style="display: none;">
                If you need ADA accommodation or cannot complete this request form please contact Community Justice Alternatives at 970.980.2600 or contact <a href="mailto:cja-records@larimer.org">cja-records@larimer.org</a>.
            </div>

            <button type="submit" class="submit-btn">Submit Request</button>
        </div>
    </form>

    <!-- Always Visible Fee Schedule -->
    <div class="fee-schedule">
        <strong>Typical Records Fees:</strong><br>
        • <strong>Documents/Records:</strong> $30/hour for search and redaction (1/2 hour Minimum & billed in ½ hour increments @ $15) + $0.25 per page copied/printed (1st 10 pages free)<br>
        • <strong>Security Camera Recording:</strong> $30.00 per hour (1 hour Minimum)
    </div>
</div>

<script>
    function handleRequestorChange() {
        const type = document.getElementById('requestorType').value;
        const mainSection = document.getElementById('section1Main');
        const clientSection = document.getElementById('clientUploadSection');
        const leoAuthSection = document.getElementById('leoAuthSection');
        const thirdPartyAuthSection = document.getElementById('thirdPartyAuthSection');
        const leoVideoNotice = document.getElementById('leoVideoNotice');
        const clientAccommodationNotice = document.getElementById('clientAccommodationNotice');
        
        const requesterNameLabel = document.getElementById('requesterNameLabel');
        const agencyGroup = document.getElementById('agencyGroup');
        const agencyInput = document.getElementById('agency');
        const titleGroup = document.getElementById('titleGroup');
        const titleInput = document.getElementById('titlePosition');
        const recordsRequestedHelp = document.getElementById('recordsRequestedHelp');

        // Hide all conditional sections
        mainSection.style.display = 'none';
        clientSection.style.display = 'none';
        leoAuthSection.style.display = 'none';
        thirdPartyAuthSection.style.display = 'none';
        leoVideoNotice.style.display = 'none';
        clientAccommodationNotice.style.display = 'none';

        // Reset required statuses
        document.getElementById('clientVerificationDoc').required = false;
        document.getElementById('identityConfirmation').required = false;
        agencyInput.required = false;
        titleInput.required = false;

        if (type === 'client') {
            mainSection.style.display = 'block';
            clientSection.style.display = 'block';
            clientAccommodationNotice.style.display = 'block';

            requesterNameLabel.textContent = 'Name';
            agencyGroup.style.display = 'none';
            titleGroup.style.display = 'none';

            recordsRequestedHelp.textContent = '(Include specific documents, program names, case numbers, & dates)';

            document.getElementById('clientVerificationDoc').required = true;
            document.getElementById('identityConfirmation').required = true;
            updateIdentityConfirmationText();

        } else if (type === 'lawEnforcement') {
            mainSection.style.display = 'block';
            leoAuthSection.style.display = 'block';
            leoVideoNotice.style.display = 'block';

            requesterNameLabel.textContent = 'Requester Name';
            agencyGroup.style.display = 'block';
            agencyInput.required = true;

            titleGroup.style.display = 'block';
            titleInput.required = true;

            recordsRequestedHelp.textContent = '(Include client/defendant name, specific documents, program names, case numbers, & dates)';
            
            togglePhiFields();

        } else if (type === 'thirdParty') {
            mainSection.style.display = 'block';
            thirdPartyAuthSection.style.display = 'block';

            requesterNameLabel.textContent = 'Requester Name';
            agencyGroup.style.display = 'block';
            agencyInput.required = true;

            titleGroup.style.display = 'none';

            recordsRequestedHelp.textContent = '(Include client/defendant name, specific documents, program names, case numbers, & dates)';

            handleThirdPartyUploadChange();
        }
    }

    function updateIdentityConfirmationText() {
        const nameVal = document.getElementById('requesterName').value.trim();
        const label = document.getElementById('identityConfirmationLabel');
        const fullName = nameVal !== '' ? nameVal : '________________';
        label.textContent = `I confirm I am ${fullName} requesting my own records`;
    }

    function togglePhiFields() {
        const isChecked = document.getElementById('phiInclusion').checked;
        const phiContainer = document.getElementById('phiFieldsContainer');
        
        if (isChecked) {
            phiContainer.style.display = 'block';
            handlePhiUploadChange();
        } else {
            phiContainer.style.display = 'none';
            document.getElementById('phiExplanation').required = false;
        }
    }

    function handlePhiUploadChange() {
        const fileInput = document.getElementById('phiAuthorizationFile');
        const explanationGroup = document.getElementById('phiExplanationGroup');
        const explanationInput = document.getElementById('phiExplanation');

        if (fileInput.files && fileInput.files.length > 0) {
            explanationGroup.style.display = 'none';
            explanationInput.required = false;
            explanationInput.value = '';
        } else {
            explanationGroup.style.display = 'block';
            explanationInput.required = true;
        }
    }

    function handleThirdPartyUploadChange() {
        const fileInput = document.getElementById('thirdPartyAuthFile');
        const explanationGroup = document.getElementById('thirdPartyExplanationGroup');
        const explanationInput = document.getElementById('thirdPartyExplanation');

        if (fileInput.files && fileInput.files.length > 0) {
            explanationGroup.style.display = 'none';
            explanationInput.required = false;
            explanationInput.value = '';
        } else {
            explanationGroup.style.display = 'block';
            explanationInput.required = true;
        }
    }
</script>

</body>
</html>
