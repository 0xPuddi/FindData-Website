<script>
    function redirectToMail() {
        window.location.href = "mailto:find.data@outlook.com?subject=Data Inquiry - Service Requested&body=Your message request";
    }
</script>

<header class="header">
    <div class="header-container">
    <img class="header-image" src="/logo_white.svg" alt="">

     <button class="header-button" on:click={redirectToMail}>
        <div>
            Contact us
        </div>
     </button>

    </div>
</header>
<slot />
<footer class="footer">
    <div class="brand-footer">
        <div class="brand-image-container-footer">
            <img class="brand-image-footer"  src="/logo_white.svg" alt="">
        </div>
        <p class="brand-text-footer">
            FindData offers any service that require, manage or extract data. Common services are: data aggregation, data analysis, scraping, APIs, neural networks fine tuning, and many more. Contact us to get any of your requests fulfilled by our expirience in the market.
        </p>
    </div>

    <div class="info-footer">
        <a href="mailto:find.data@outlook.com?subject=Data Inquiry - Service Requested&body=Your message request">
            <p class="info-text-footer">Email</p>
        </a>
        <a href="https:/twitter.com/FindData_" target="_blank">
            <p class="info-text-footer">Twitter</p>
        </a>
        
    </div>
</footer>

<style>
    :global(body) {
        margin: 0;
        background-color: black;
    }
    :global(h1, h2, h3, p) {
        font-family: Arial, Helvetica, sans-serif;
        margin: 0;
    }
    :global(a) {
        text-decoration: none;
    }
    p {
        color: white;
    }

    .header {
        z-index: 999;

        position: fixed;

        width: 100%;
        height: 60px;
        background-color: rgba(0, 0, 0, 1);

        display: flex;
        align-items: center;
        justify-content: center;
    }
    .header-container {
        display: flex;
        align-items: center;
        justify-content: space-between;

        width: 75%;
    }
    .header-image {
        width: 36px;
        height: 36px;
    }
    .header-button {
        position: relative;

        height: 35px;
        width: 90px;

        cursor: pointer;

        display: flex;
        align-items: center;
        justify-content: center;

        background-color: transparent;
        border: 2px solid white;
        color: white;

        border-radius: 9px;

        transition: all 125ms;
    }
    .header-button:hover, .header-button:focus {
        box-shadow: 
        inset -2.75rem 0 0 0 #141f52,
        inset 2.75rem 0 0 0 #141f52;  
    }

    .footer {
        width: 100%;
        height: 150px;

        background-color: black;

        display: flex;
        align-items: center;
        justify-content: space-around;
        gap: 2rem;
    }

    .brand-footer {
        width: 65%;
        height: 100%;

        display: flex;
        flex-direction: row;
        align-items: flex-start;
        justify-content: center;
        gap: 1rem;

        margin-left: 5px;
    }
    .brand-image-container-footer {
        display: flex;
        align-items: center;
        justify-content: center;

        height: 100%;
    }
    .brand-image-footer {
        width: 48px;
        height: 48px;
    }
    .brand-text-footer {
        display: flex;
        align-items: center;
        justify-content: center;

        width: 100%;
        height: 100%;

        font-size: small;

    }
    @media (max-width: 900px) {
    .brand-text-footer {
        font-size: x-small;
    }
    }
    .info-footer {
        width: 20%;

        display: flex;
        flex-direction: column;
        align-items: flex-start;

        margin-right: 5px;
        gap: 1rem;
    }
    .info-text-footer {
        cursor: pointer;

        font-size: medium;
        font-weight: lighter;

        border-bottom: 2px solid;
        border-color: rgba(255, 255, 255, 0);

        transition: all 225ms;
    }
    .info-text-footer:hover {
        border-color: rgba(255, 255, 255, 1);
    }

</style>