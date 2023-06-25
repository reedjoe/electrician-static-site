<script lang="ts">
    import logo from "$lib/images/jarvis_electrical_logo.jpg";
    import telephone from "$lib/icons/telephone.svg";
    import email from "$lib/icons/email.svg";
    import facebook from "$lib/icons/facebook.svg";
	import { phoneNumber, emailAddress, facebookUrl, facebookProfileName } from "$lib/constants";

    let currentYear = new Date().getFullYear().toString();
</script>

<footer>
    <div class="content_wrapper">
        <img class="logo" src={logo} alt="jarvis electrical services logo" />
        <div class="message">
            <h4>Get in contact with us</h4>
            <p>
                To discuss your requirements please give us a call or send us an
                email
            </p>
        </div>
        <div class="contact">
            <a href="tel:+{phoneNumber}">
                <img class="telephone" src={telephone} alt="Telephone number" />
                {phoneNumber}
            </a>
            <a href="mailto:{emailAddress}">
                <img class="email" src={email} alt="Email address" />
                {emailAddress}
            </a>
            <a href="{facebookUrl}">
                <img class="facebook" src={facebook} alt="Facebook account" />
                {facebookProfileName}
            </a>
        </div>
    </div>
    <p class="copyright">Site created by Joe Reed © {currentYear}</p>
</footer>

<style>
    footer {
        width: 100%;
        background-color: #3b3f40f6;
        color: rgba(244, 244, 244, 0.876);
    }

    .content_wrapper {
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;
        gap: 25px;
    }

    .content_wrapper div {
        max-width: 280px;
    }

    .logo {
        width: 200px;
    }

    .message h4 {
        font-size: 24px;
        margin-top: 0;
        margin-bottom: 20px;
    }

    .contact {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        gap: 15px;
    }

    .contact a:first-child {
        margin-top: 0;
    }

    .contact a {
        display: inline-flex;
        gap: 10px;
        color: rgba(244, 244, 244, 0.876);
        word-break: break-word;
    }

    .copyright {
        font-size: 14px;
        padding-right: 15px;
        text-align: end;
    }

    @media screen and (min-width: 900px) {
        .logo {
            width: 300px;
        }

        .content_wrapper {
            padding: 40px;
            flex-direction: row;
        }

        .contact a {
            word-break: normal;
        }
    }
</style>
