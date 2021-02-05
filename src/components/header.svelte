<script>
    import Github from '../assets/github.svg';
    import Linkedin from '../assets/linkedin.svg';
    import Printer from '../assets/printer.svg';
</script>

<nav class="navbar navbar-light bg-light d-print-none">
    <div class="container-fluid">
        <div class="d-none d-sm-block"></div>
        <div class="navbar-text social-btns-div">
            <!-- svelte-ignore a11y-invalid-attribute -->
            <a href="javascript:void(0);" on:click={()=> window.print()} title="print" role="button" class="social-link">
                <Printer width="20"/>
            </a>
            <a href="https://github.com/vipinsaini1989" target="_blank" title="github" class="social-link">
                <Github width="20"/>
            </a>
            <a href="www.linkedin.com/in/vipin-saini-76a76765" target="_blank" title="linkedin" class="social-link">
                <Linkedin width="20"/>
            </a>
        </div>
    </div>
  </nav>

  <style>
      .social-link{
        border: 1px solid var(--bs-dark);
        padding: .6rem;
        border-radius: 50%;
        margin-left: .5rem;
      }

      .social-link:hover{
        color: var(--bs-primary) !important;
        border: 1px solid var(--bs-primary);
      }
  </style>