
  <head xmlns="http://www.w3.org/1999/xhtml">
    <meta http-equiv="Content-Security-Policy" content="default-src chrome:; object-src 'none'" />
    <meta name="color-scheme" content="light dark" />
    <title>Problem loading page</title>
    <link rel="stylesheet" href="chrome://browser/skin/aboutNetError.css" type="text/css" media="all" />
    <link rel="icon" id="favicon" href="chrome://global/skin/icons/info.svg" />
    <link rel="localization" href="browser/aboutCertError.ftl" />
    <link rel="localization" href="browser/nsserrors.ftl" />
    <link rel="localization" href="branding/brand.ftl" />
  </head>

  <body xmlns="http://www.w3.org/1999/xhtml" dir="ltr" class="neterror">
    <!-- ERROR ITEM CONTAINER (removed during loading to avoid bug 39098) -->
    

    <!-- PAGE CONTAINER (for styling purposes only) -->
    <div id="errorPageContainer" class="container">
      <div id="text-container">
        <!-- Error Title -->
        <div class="title">
          <h1 class="title-text" data-l10n-id="connectionFailure-title">Unable to connect</h1>
        </div>

        <!-- LONG CONTENT (the section most likely to require scrolling) -->
        <div id="errorLongContent">

          <!-- Short Description -->
          <div id="errorShortDesc">
            <p id="errorShortDescText">Firefox can’t establish a connection to the server at 127.0.0.1:4444.</p>
          </div>

          <div id="errorShortDesc2">
              <p id="errorShortDescText2"></p>
          </div>

          <div id="errorWhatToDoTitle">
              <p id="errorWhatToDoTitleText"></p>
          </div>

          <div id="errorWhatToDo">
              <p id="badStsCertExplanation" hidden="true"><span class="hostname"></span> has a security policy called HTTP Strict Transport Security (HSTS), which means that Firefox can only connect to it securely. You can’t add an exception to visit this site.</p>
              <p id="errorWhatToDoText"></p>
          </div>

          <div id="errorWhatToDo2">
              <p id="errorWhatToDoText2"></p>
              <p id="badStsCertExplanation" hidden="true"><span class="hostname"></span> has a security policy called HTTP Strict Transport Security (HSTS), which means that Firefox can only connect to it securely. You can’t add an exception to visit this site.</p>
          </div>

          <!-- Long Description (Note: See netError.dtd for used XHTML tags) -->
          <div id="errorLongDesc">
<ul xmlns="http://www.w3.org/1999/xhtml">
  <li>The site could be temporarily unavailable or too busy. Try again in a few
    moments.</li>
  <li>If you are unable to load any pages, check your computer’s network
    connection.</li>
  <li>If your computer or network is protected by a firewall or proxy, make sure
    that Firefox is permitted to access the Web.</li>
</ul>
</div>

          <div id="tlsVersionNotice" hidden="true">
            <p data-l10n-id="cert-error-old-tls-version">This website might not support the TLS 1.2 protocol, which is the minimum version supported by Firefox.</p>
          </div>

          <div id="learnMoreContainer">
            <p><a id="learnMoreLink" target="_blank" rel="noopener noreferrer" data-telemetry-id="learn_more_link" href="https://support.mozilla.org/1/firefox/102.11.0/Linux/en-US/connection-not-secure">Learn more…</a></p>
          </div>

          <div id="openInNewWindowContainer" class="button-container">
            <p><a id="openInNewWindowButton" target="_blank" rel="noopener noreferrer">
            <button class="primary" data-l10n-id="open-in-new-window-for-csp-or-xfo-error">Open Site in New Window</button></a></p>
          </div>
        </div>

        <!-- UI for option to report certificate errors to Mozilla. Removed on
             init for other error types .-->
        <div id="prefChangeContainer" class="button-container">
          <p>It looks like your network security settings might be causing this. Do you want the default settings to be restored?</p>
          <button id="prefResetButton" class="primary">Restore default settings</button>
        </div>

        <div id="certErrorAndCaptivePortalButtonContainer" class="button-container">
          <button id="returnButton" class="primary" data-telemetry-id="return_button_top">Go Back (Recommended)</button>
          <button id="openPortalLoginPageButton" class="primary">Open Network Login Page</button>
          <button class="primary try-again">Try Again</button>
          <button id="advancedButton" data-telemetry-id="advanced_button">Advanced…</button>
        </div>
      </div>

      <div id="netErrorButtonContainer" class="button-container"><button class="primary try-again">Try Again</button>
        
      </div>

      <div id="advancedPanelContainer">
        <div id="badCertAdvancedPanel" class="advanced-panel" hidden="">
          <p id="badCertTechnicalInfo"></p>
          <a id="viewCertificate" href="javascript:void(0)">View Certificate</a>
          <div id="advancedPanelButtonContainer" class="button-container">
            <button id="advancedPanelReturnButton" class="primary" data-telemetry-id="return_button_adv">Go Back (Recommended)</button>
            <button class="primary try-again">Try Again</button>
            <div class="exceptionDialogButtonContainer">
              <button id="exceptionDialogButton" data-telemetry-id="exception_button">Accept the Risk and Continue</button>
            </div>
          </div>
        </div>

        <div id="blockingErrorReporting" class="advanced-panel" hidden="">
            <p class="toggle-container-with-text">
                <input type="checkbox" id="automaticallyReportBlockingInFuture" role="checkbox" />
                <label for="automaticallyReportBlockingInFuture">Report errors like this to help Mozilla identify and block malicious sites</label>
            </p>
        </div>

        <div id="certificateErrorDebugInformation" class="advanced-panel" hidden="">
          <button id="copyToClipboardTop" data-telemetry-id="clipboard_button_top">Copy text to clipboard</button>
          <div id="certificateErrorText"></div>
          <button id="copyToClipboardBottom" data-telemetry-id="clipboard_button_bot">Copy text to clipboard</button>
        </div>
      </div>
    </div>
  </body>
  <script xmlns="http://www.w3.org/1999/xhtml" src="chrome://browser/content/certerror/aboutNetErrorCodes.js"></script>
  <script xmlns="http://www.w3.org/1999/xhtml" type="module" src="chrome://browser/content/certerror/aboutNetError.js"></script>
