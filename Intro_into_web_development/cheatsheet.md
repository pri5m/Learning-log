# JS validation
```
<script>
      function filloutForm() {
          var name = document.forms["getInTouch"]["name"].value;
          var tel = document.forms["getInTouch"]["tel"].value;
          if (name == "") {
            alert("Name must be filled out");
            return false;
          }
          if (tel == "") {
            alert("Telephone must be filled out");
            return false;
          }
          return telValidation();
      }
      /* Adapted from: https://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_number (retrived: 1/11/17) */
      function telValidation(){
        var tel = document.forms["getInTouch"]["tel"].value;
        // Could use regular expression instead //
        if (isNaN(tel) || x < 1 || x > 10) {
          alert("Please use numbers and numbers only");
          return false;
        }
      }
    </script>
```
