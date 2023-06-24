<script>
    import down_arrow from "$lib/icons/down-arrow.svg";
</script>

<div class="cover-photo">
    <div class="wrapper">
        <h1>Electrician services</h1>
        <h3>From large projects to simple wiring jobs, we can cater for your needs</h3>
        <a href="/services" class="contact-button">View Services</a>
    </div>
    <a href="#main-content"><img class="down-arrow" src={down_arrow} alt="Down" /></a>
</div>

<style>
	.cover-photo {
		min-height: 100vh;
		background-image: url($lib/images/patrick-tomasso-1NTFSnV-KLs-unsplash.jpg);
		background-size: cover;  
		background-repeat: no-repeat;
  		background-size: auto;
		background-position: center center;
        background-color: rgba(49, 32, 15, 0.5);
        background-blend-mode: multiply;
        /* position: relative; */
	}

    .wrapper {
        position: absolute;
        top: 35%;
        /* background-color: rgba(22, 22, 21, 0.873); */
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

    .down-arrow {
        bottom: 30px;
        position: absolute;
        margin-left: auto;
        margin-right: auto;
        left: 0;
        right: 0;
        text-align: center;
    }

    @media screen and (min-width: 600px) {
        .wrapper {
            left: 10%;
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
</style>
