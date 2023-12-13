<script src="https://unpkg.com/launchdarkly-js-client-sdk@2.18.1/dist/ldclient.min.js"></script>

<h1>Test By Joey</h1>

<div id="preview" style="display:none">
  <p>
    this is for feature toggle testing.
  </p>
</div>

<script>
   var clientId = "6579632af1ad7f0fffccf92b";
   var falgName = "testfeatureflag";
   var Idclient = window.LDClient.initialize(clientId, user);

   Idclient.on("ready", function() {
     document.getElementById("preview").style.display = Idclient.variation(flagname, false) ?
     "block":"none";
   });

   Idclient.on("change":"+ flagname, function(newVal, prevVal) {
     docuement.getElementById("preview").style.display = newVal ? "block":"none";
   });
</script>
