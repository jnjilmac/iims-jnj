<!-- https://picocss.com/docs/forms.html -->
<script>
  import { onMount } from 'svelte';

  let withdraw = 0;
  let deposit = 0;
  onMount(() => {
    document.getElementById('indeterminate-checkbox').indeterminate = true;
  });
</script>

<fieldset>
  <label for="terms">
    <input type="checkbox" id="indeterminate-checkbox" name="terms" />
    I agree to the Terms and Conditions
  </label>
</fieldset>
