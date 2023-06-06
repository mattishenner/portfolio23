<form action="https://formsubmit.co/e1a3e07c005c0bfba6db99801f37aa74" method="POST">
    <!-- Honeypot -->
    <input type="text" name="_honey" style="display: none;">

    <!-- Disable captcha -->
    <input type="hidden" name="_captcha" value="false">

    <!-- Thank you page -->
    <input type="hidden" name="_next" value="https://www.mattishenner.dk/tak.html">

    <!-- Auto response -->
    <input type="hidden" name="_autoresponse" value="Hey! Tak for din besked. Jeg skal nok sørge for at vende hurtigt tilbage.">
    
    <input type="text" id="name" name="name" placeholder="Navn" required>
    <input type="email" id="email" name="email" placeholder="E-mail" required>
    <textarea name="message" id="message" placeholder="Besked" required></textarea>
    <button type="submit">Send</button>
</form>

<style>
    form{
        display: flex;
        flex-direction: column;
        gap: 10px;
        min-width: 50%;
    }
    input{
        background-color: transparent;
        /* background-color: #f1f1f1; */
        border: none;
        border-bottom: 2px solid var(--black);
        /* padding: 10px; */
        font-size: 1em;
        /* border-radius: calc(var(--border-radius) / 2); */
    }
    input::placeholder{
        color: var(--black);
    }
    input:focus{
        outline-color: var(--green);
    }
    textarea{
        font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        resize: none;
        background-color: transparent;
        /* background-color: #f1f1f1; */
        border: none;
        border-bottom: 2px solid var(--black);
        /* padding: 10px; */
        font-size: 1em;
        /* border-radius: calc(var(--border-radius) / 2); */
        height: 170px;
    }
    textarea::placeholder{
        color: var(--black);
        position: relative;
        top: 150px;
    }
    textarea:focus{
        outline-color: var(--green);
    }
    button{
        cursor: pointer;
        font-size: 1em;
        padding: 10px;
        background-color: var(--black);
        border: none;
        border-radius: calc(var(--border-radius) / 2);
        color: var(--white);
    }

    @media only screen and (max-width: 768px){
        form{
            width: 100%;
            margin: 0 var(--margin);
        }
    }
</style>