<script setup>

</script>

<template>
    <section>
        <article class="foodIntro">
            <img src="../assets/img/spisningHeader.png" alt="hero billede til spisning med buffet">
            <h1>Spisning</h1>
            <p>Hos Action House Funcenter kan I nyde lækker mad og forfriskninger midt i al actionen. Vores spisested er perfekt til at samle energi, hygge jer og fortsætte sjove oplevelser sammen - uanset om det er familie, venner eller kolleger.</p>
        </article>
    </section>
    <section>
        <article class="menuContainer">
            <h2>Pakketilbud menuer</h2>
            <p>vælg mellem:</p>
            <ul>
                <li>Steak af oksefilet med bearnaise sauce (pris uden aktiviteter 199,-)</li>
                <li>Grillet kyllingebryst med whiskey sauce (pris uden aktiviteter 179,-)</li>
            </ul>
            <p>Begge menuer vil blive serveret med frisk salat, dagens kartoffel og grønsager .</p>
            <ul>
                <li>Crispy kylling inderfileter med pommes frites og salat (pris uden aktiviteter 109,-)</li>
                <li>Burger med pommes frites (pris uden aktiviteter 159,-)</li>
                <li>Pizza (vælg mellem skinke, pepperoni el. kebab) (pris uden aktiviteter 89,-)</li>
            </ul>
            <p>Vi gør opmærksom på at man ikke kan forvente at få lokalet alene til denne pris for denne menu, ved selskaber i eget lokale henviser vi til vores selskabsbuffeter.</p>
            <p>Vi har fornyligt fået nyt sodavands og fadølsanlæg og kan derfor tilbyde hele 12 forskellige slags fadøl
            Se vores spændende drikkevarer her
            Få oplysninger om allergener ved at kontakt personalet
            Se vores smiley og rapport her </p>
            <div class="imgContianer">
                <img src="../assets/img/spisning-Bar.jpg" alt="mand der står bag en bar">
                <img src="../assets/img/spisning-Drikkevarer.jpg" alt="udvalg af drikke varer i baren">
            </div>
        </article>
    </section>
    <section>
        <article class="buffetContainer">
            <h2>Vores populære hjemmelavet buffeter</h2>
            <div class="buffetMad">
                <ul>
                    <li>Tunmousse</li>
                    <li>Sprød kyllingesalat</li>
                    <li>Hjemmelavet pizza</li>
                    <li>Ovnbagt laks</li>
                    <li>Steg af oksefilet</li>
                    <li>Flødekartofler, steakfritter, brancherede grøntsager, 2 slags sauce.</li>
                    <li>Stor salatbar m/ bl.a. pastasalat, rødkålssalat, revet gulerødder, majs, ærter, croutoner, broccoli, coleslaw, oliven, marinerede hvidløg, soltørrede tomater, karry ris, rødkålssalat og dressinger.</li>
                    <li>Friskbagt brød og smør.</li>
                </ul>
                <p>Bemærk udvalget kan variere.</p>
                <p>Der kan nu tilkøbes fri softice dage der er buffet for kun 29,- pr. pers.</p>
            </div>
            <div class="buffetImg">
                <img src="../assets/img/spisning-Buffet.png" alt="billede af salatbar i buffeten">
            </div>
        </article>
    </section>
    <section>
        <article class="buffetContainer">
            <h2>Julebuffet</h2>
            <div class="buffetMad">
                <p>Fra d. 1. November frem til d. 20. december serverer vi vores populære julebuffet.</p>
                <p>(pris m. aktiviteter 200,- og pris u. aktiviteter 229,- for voksne og 89,- for børn under 12 år)</p>
                <p>Ring og hør nærmere om, hvilket dage vi servere denne buffet i vores restaurant til vores pakker</p>
                <h3>På julebuffeten er der bl.a:</h3>
                <ul>
                    <li>Marineret sild og karrysild</li>
                    <li>Fiskefilet m. remoulade</li>
                    <li>Medister- og flæskestegspålæg med syltet rødkål</li>
                    <li>Rejer m. mayonnaise</li>
                    <li>Tarteletter m/ høns i asparges</li>
                    <li>Fiskefad m/dressing</li>
                    <li>Brunede kartofler</li>
                    <li>Svinekam og glaseret skinke m. grønlangkål og kanelsukker</li>
                    <li>Ris a la mande med kirsebærsauce</li>
                </ul>
            </div>
            <div class="juleBuffetImg">
                <img src="../assets/img/spisning-julebuffet.png" alt="billede af buffet fra Action House">
            </div>
        </article>
    </section>
</template>

<style scoped>
    .foodIntro{
        display: flex;
        flex-direction: column;
        align-items: center;

    }

    .foodIntro h1{
        color: var(--mainblue);
    }

    .foodIntro p{
        width: 70ch;
    }

    .foodIntro img{
        width: 100vw;
        height: 60vh;
        object-fit: cover;
    }

    .menuContainer{
        display: flex;
        flex-direction: column;
        margin-left: 100px;
    }

    h2{
        color: var(--mainblue);
    }

    p{
        width: 70ch;
        line-height: 30px;
        font-weight: 400;
        margin-top: 1rem;
    }

    ul{
        margin-top: 0.5rem;
        line-height: 30px;
        font-size: 1.2rem;
    }

    .imgContianer{
        display: flex;
        justify-content: space-evenly;
        margin-top: 2rem;
    }

    .imgContianer img{
        max-width: 30vw;
        max-height: 70vh;
        border-radius: 10px;
    }

    .buffetMad ul{
        width: 55ch;
        line-height: 3rem;
        font-size: 1.2rem;
    }

    .buffetMad p{
        max-width: 70ch;
        line-height: 30px;
        font-weight: 400;
        margin-top: 1rem;
    }


    .buffetContainer{
        display: grid;
        grid-template-columns: 1fr, 1fr;
        grid-template-rows: 1fr, 1fr;
        margin-top: 4rem;
        margin-left: 100px;
        margin-right: 100px;
    }

    .buffetContainer h2{
        grid-column: 1 / 2;
        grid-row: 1 / 1;
    }

    .buffetContainer .buffetMad{
        grid-column: 1 / 2;
        grid-row: 2 / 2;
    } 

    .buffetContainer .buffetImg{
        grid-column: 2 / 3;
        grid-row: 2 / 2;
        display: flex;
        justify-content: flex-end;
    }

    .buffetContainer .buffetImg img{
        max-width: 501px;
    }
    .buffetContainer .juleBuffetImg{
        grid-column: 2 / 3;
        grid-row: 2 / 2;
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }
    

</style>