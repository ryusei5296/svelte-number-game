<script>
    export let buttonName = '村人A'
</script>

<input type="text" placeholder="{buttonName}">

<style>
    input {
        text-align: center;
        font-family: inherit;
        font-size: inherit;
        font-weight: bold;
        padding: 1em 2em;
        color: #ff0000;
        background-color: rgba(255, 136, 171, 0.1);
        border-radius: 1em;
        border: 2px solid rgba(255, 62, 0, 0);
        outline: none;
        width: 450px;
        cursor: pointer;
  }

  input:focus {
    border: 2px solid #ff3e00;
  }
</style>