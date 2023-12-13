<script src="https://unpkg.com/launchdarkly-js-client-sdk@2.18.1/dist/ldclient.min.js"></script>

<h1>Test By Joey</h1>

<div id="preview" style="display:none">
  <p>
    This is for feature toggle testing to check when toggle on and off.
  </p>
</div>

<script>
   var clientId = "6579632af1ad7f0fffccf92b";
   var flagName = "testfeatureflag";
   var user = { anonymous: true };
   var ldclient = window.LDClient.initialize(clientId, user);

   ldclient.on("ready", function() {
     document.getElementById("preview").style.display = ldclient.variation(flagName, false) ?
     "block":"none";
   });

   ldclient.on("change:" + flagName, function(newVal, prevVal) {
     document.getElementById("preview").style.display = newVal ? "block":"none";
   });
  
</script>
