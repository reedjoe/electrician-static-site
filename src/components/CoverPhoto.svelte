<script lang="ts">
    import down_arrow from "$lib/icons/down-arrow.svg";
	import { emailAddress } from "$lib/constants";
</script>

<div class="cover-photo">
    <div class="wrapper">
        <h1>Electrician services</h1>
        <h3>From large projects to simple wiring jobs, we can cater for your needs</h3>
        <a href="/services" class="contact-button">View Services</a>
    </div>
    <a href="#main-content"><img class="down-arrow" src={down_arrow} alt="Down" /></a>
    <div class="email">
        <a href="mailto:{emailAddress}">
            {emailAddress}
        </a>
    </div>
</div>

<style>
	.cover-photo {
		min-height: 100vh;
		min-height: 100svh;

		background-image: url($lib/images/patrick-tomasso-1NTFSnV-KLs-unsplash.jpg);
		background-size: cover;  
		background-repeat: no-repeat;
		background-position: center center;
        background-color: rgba(49, 32, 15, 0.5);
        background-blend-mode: multiply;
	}

    .wrapper {
        position: absolute;
        top: 30%;
        color: rgba(244, 244, 244, 0.876);
        max-width: 400px;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        padding: 10px;
    }

    h1 {
        font-size: 42px;
        text-transform: uppercase;
        text-align: start;
        margin: 0;
        margin-bottom: 25px;
    }

    h3 {
        font-size: 16px;
        text-align: start;
        margin: 0;
        margin-bottom: 15px;
    }

    .contact-button {
        max-width: 200px;
        padding: 10px;
        cursor: pointer;
        color: rgba(244, 244, 244, 0.876);
        font-weight: bold;
        font-size: 18px;
        text-align: center;
        text-decoration: none;
        border: 1px solid rgba(244, 244, 244, 0.876);
        background-color: transparent;
        box-shadow: 0 6px 6px rgba(0, 0, 0, 0.6);
    }

    .contact-button:hover {
        background-color:rgba(61, 61, 61, 0.274);
        -webkit-transition: background-color 200ms linear;
        -ms-transition: background-color 200ms linear;
        transition: background-color 200ms linear;
        
        box-shadow: 0 8px 8px rgba(0, 0, 0, 0.6);
        -webkit-transition: box-shadow 100ms ease-out;
        -ms-transition: box-shadow 100ms ease-out;
        transition: box-shadow 100ms ease-out;
    }

    .down-arrow {
        bottom: 80px;
        position: absolute;
        margin-left: auto;
        margin-right: auto;
        left: 0;
        right: 0;
        text-align: center;
    }

    .email {
        position: absolute;
        right: 0;
        bottom: 0;
        width: 300px;
        height: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: rgba(72, 72, 72, 0.361);
        border-radius: 15px 0 0 0;
    }

    .email a {
        display: inline-flex;
        gap: 10px;
        color: var(--color-theme-1);
        font-size: 16px;;
    }

    @media screen and (min-width: 600px) {
        .wrapper {
            left: 10%;
            top: 35%;
        }

        h1 {
            font-size: 62px;
            margin-bottom: 25px;
        }

        h3 {
            font-size: 18px;
            margin-bottom: 15px;
        }

        .contact-button {
            font-size: 22px;
        }
    }

    @media screen and (min-width: 800px) {
        .down-arrow {
            bottom: 30px;
        }

        .email {
            width: 350px;
            border-radius: 15px 0 0 0;
        }

        .email a {
            font-size: 18px;;
        }
    }
</style>
