<script src="https://unpkg.com/launchdarkly-js-client-sdk@2.18.1/dist/ldclient.min.js"></script>

<h1>Test By Joey</h1>
<div id="test1" style="display:true">
  <p>
    this is for feature toggle testing_1.
  </p>
</div>

<div id="preview" style="display:none">
  <p>
    this is for feature toggle testing.
  </p>
</div>

<script>
   var clientId = "6579632af1ad7f0fffccf92b";
   var falgName = "testfeatureflag";
   var user = {anonymous: true};
   var ldclient = window.LDClient.initialize(clientId, user);

   ldclient.on("ready", function() {
     document.getElementById("preview").style.display = ldclient.variation(flagname, false) ?
     "block":"none";
   });

   ldclient.on("change":"+ flagname, function(newVal, prevVal) {
     docuement.getElementById("preview").style.display = newVal ? "block":"none";
   });
</script>
