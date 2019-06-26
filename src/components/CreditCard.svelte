<script>
    import { fade } from 'svelte/transition';
    export let logo;

    let visa = 'data:image/png;base64,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';
    let chip =  'data:image/png;base64,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';
    let masterCard = 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGQAAABkCAYAAABw4pVUAAABN2lDQ1BBZG9iZSBSR0IgKDE5OTgpAAAokZWPv0rDUBSHvxtFxaFWCOLgcCdRUGzVwYxJW4ogWKtDkq1JQ5ViEm6uf/oQjm4dXNx9AidHwUHxCXwDxamDQ4QMBYvf9J3fORzOAaNi152GUYbzWKt205Gu58vZF2aYAoBOmKV2q3UAECdxxBjf7wiA10277jTG+38yH6ZKAyNguxtlIYgK0L/SqQYxBMygn2oQD4CpTto1EE9AqZf7G1AKcv8ASsr1fBBfgNlzPR+MOcAMcl8BTB1da4Bakg7UWe9Uy6plWdLuJkEkjweZjs4zuR+HiUoT1dFRF8jvA2AxH2w3HblWtay99X/+PRHX82Vun0cIQCw9F1lBeKEuf1UYO5PrYsdwGQ7vYXpUZLs3cLcBC7dFtlqF8hY8Dn8AwMZP/fNTP8gAAAAJcEhZcwAADsQAAA7EAZUrDhsAAATzaVRYdFhNTDpjb20uYWRvYmUueG1wAAAAAAA8P3hwYWNrZXQgYmVnaW49Iu+7vyIgaWQ9Ilc1TTBNcENlaGlIenJlU3pOVGN6a2M5ZCI/PiA8eDp4bXBtZXRhIHhtbG5zOng9ImFkb2JlOm5zOm1ldGEvIiB4OnhtcHRrPSJBZG9iZSBYTVAgQ29yZSA1LjYtYzE0NSA3OS4xNjM0OTksIDIwMTgvMDgvMTMtMTY6NDA6MjIgICAgICAgICI+IDxyZGY6UkRGIHhtbG5zOnJkZj0iaHR0cDovL3d3dy53My5vcmcvMTk5OS8wMi8yMi1yZGYtc3ludGF4LW5zIyI+IDxyZGY6RGVzY3JpcHRpb24gcmRmOmFib3V0PSIiIHhtbG5zOnhtcD0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wLyIgeG1sbnM6ZGM9Imh0dHA6Ly9wdXJsLm9yZy9kYy9lbGVtZW50cy8xLjEvIiB4bWxuczpwaG90b3Nob3A9Imh0dHA6Ly9ucy5hZG9iZS5jb20vcGhvdG9zaG9wLzEuMC8iIHhtbG5zOnhtcE1NPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvbW0vIiB4bWxuczpzdEV2dD0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL3NUeXBlL1Jlc291cmNlRXZlbnQjIiB4bXA6Q3JlYXRvclRvb2w9IkFkb2JlIFBob3Rvc2hvcCBDQyAyMDE5IChXaW5kb3dzKSIgeG1wOkNyZWF0ZURhdGU9IjIwMTktMDYtMTdUMTc6MTU6NDEtMDU6MDAiIHhtcDpNb2RpZnlEYXRlPSIyMDE5LTA2LTE3VDE3OjE5OjU1LTA1OjAwIiB4bXA6TWV0YWRhdGFEYXRlPSIyMDE5LTA2LTE3VDE3OjE5OjU1LTA1OjAwIiBkYzpmb3JtYXQ9ImltYWdlL3BuZyIgcGhvdG9zaG9wOkNvbG9yTW9kZT0iMyIgeG1wTU06SW5zdGFuY2VJRD0ieG1wLmlpZDo3NDk2YTA3ZC1iZjAzLTliNDgtYmY2Mi1hMGZjODU4NTMzNGYiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6NzQ5NmEwN2QtYmYwMy05YjQ4LWJmNjItYTBmYzg1ODUzMzRmIiB4bXBNTTpPcmlnaW5hbERvY3VtZW50SUQ9InhtcC5kaWQ6NzQ5NmEwN2QtYmYwMy05YjQ4LWJmNjItYTBmYzg1ODUzMzRmIj4gPHhtcE1NOkhpc3Rvcnk+IDxyZGY6U2VxPiA8cmRmOmxpIHN0RXZ0OmFjdGlvbj0iY3JlYXRlZCIgc3RFdnQ6aW5zdGFuY2VJRD0ieG1wLmlpZDo3NDk2YTA3ZC1iZjAzLTliNDgtYmY2Mi1hMGZjODU4NTMzNGYiIHN0RXZ0OndoZW49IjIwMTktMDYtMTdUMTc6MTU6NDEtMDU6MDAiIHN0RXZ0OnNvZnR3YXJlQWdlbnQ9IkFkb2JlIFBob3Rvc2hvcCBDQyAyMDE5IChXaW5kb3dzKSIvPiA8L3JkZjpTZXE+IDwveG1wTU06SGlzdG9yeT4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz6ys9xXAAAcJElEQVR4nO2daZBdx3Xff6f73vvemzc7BhgAAwIgAQIUCVKUSEoqy7KlIkVKtrbEkWI5ZcUVl5XITqIkivLJ/pJKVRapSonjOFGqYskVx0ocU7IcSdZCaqUcCaLCXQQIEPsODGZ9y126Tz70fTNvNhAkMcP5MP+qW8S8+969p/vffc7p06cPRVXZwPqB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'
    let visaTest =  /^4[0-9]{4}/;
    let maesterCardTest = /^5[0-9]{4}/;
    let company = '';
    let src = '';
    let digits = '';
    let digitsFormated = '';
    let month = '';
    let year = '';
    let name = '';
    let message = '';
    let date = new Date();
    let fullYear = date.getFullYear();
    let monthNumber = date.getMonth() + 1;
    let showForm = true;
    let visible = false;

    // Verificar que tipo de tarjeta es y colocar logo

    $: if (visaTest.test(digits)) {
        src = visa;   
	} else if(maesterCardTest.test(digits)) {
        src = masterCard;
    }

    // formatear dígitos de 4 en 4

	function formatDigits(event) {

        digits = event.target.value;
        if(digits == ''){
            digitsFormated = '';
        } else {
            let numbers = digits.match(/.{1,4}/g);
            digitsFormated = numbers.join(' ');
        }
    }
    // Vaidamos:
    function validate() {

        if( digits == '' || digits.length !== 16){ // que los dígitos sean 16
            message = 'Verifique los dígitos de su tarjeta';
            return false;
        } else if (name == '' || name.length < 5 ) { // Que el nombre no sea menor a 5
            message = 'Verifique el nombre';
            return false;
        } else if (month == '' || month.length < 1) { // que el mes no esté vacío y su longitud no sea menos a 1
            message = 'Verifique el mes de expiración';
            return false;
        } else if (month < monthNumber && year == fullYear){ // que el mes no sea menor al actual en el año actual
            message = 'Verifique el mes de expiración';
            return false;
        }
        else if( year == '' || year.length < 4 || year < fullYear) { // que el año no esté vacío, el length no sea menor a 4 y no sea menor a el año
            message = 'Verifique el año de expiración';
            return false;
        } else {
            message = '';
            return true;
        }
    }

    function add() {

        let valid = validate();
        if(valid) {
            digits = '';
            name = '';
            month = '';
            year = '';
            showForm = false;
            visible = true;
        }
    }

    function back(){
        visible= false;
        showForm= true;
    }

</script>

<style lang="scss">

.credit-card {
    display:grid;
    grid-template-columns: 1fr;
    padding: 1rem;
    justify-content:center;
    grid-gap:1rem;

    @media (min-width: 760px) {
        grid-template-columns: repeat(2, 1fr);
        align-items: center; 
        justify-content:center;
    } 

    .card-container{
        padding: 1rem;
        justify-self: center;
        .card {
            background-color: #2750af;
            padding: .5rem;
            border-radius: 1rem;
            height: 12rem;
            width:23rem;
            display:grid;
            grid-template-columns: 1fr;
            grid-template-rows: 30% 25% 15% 20% 10%;
            color:white;
            box-shadow: 0px 1px 10px #999;

            .logo-container {
                // background-image: url(http://www.librosweb.es/website/css/images/logo.gif); NO FUNCIONA
               // background-repeat: no-repeat;
              //  background-color: #fff; FUNCIONA SOLO CON COLORES
              .logo {
                  display:flex;
                  justify-content: space-between;
                  margin-top: .3rem;
                  .company {
                    max-width:10%;
                    margin-right: .5rem;
                  }

                .coderos {
                    max-width:10% !important;
                    margin-left: 1rem;
                }
              }
            }

            .chip {
                margin-left: .5rem;
                img {
                    max-width: 15%;
                }
            }

            .digits {
                padding-top: .5rem;
                margin-left: 1rem;
                font-size: 1.1rem;
                float: left;
                letter-spacing: 3px;
                    text-align: center;
                    span {
                        &:nth-child(4n){
                            margin-right:.3rem;
                            color:red;
                        }
                    }
            }

            .expiration {
                padding: .8rem 0 .8rem 0;
                font-size: .8rem;
                text-align:center;

                span {
                    font-size: .6rem;
                }
            }

            .name {
                text-align:center;
                font-size: .8rem;
                padding-bottom: 1rem;
            }

            @media (max-width: 460px) {
                width:14rem;
            }

        }
    }

    .info {
        padding-top: 1rem;
        text-align: center;
        
        h1 {
            font-size: 1.3rem;
        }

        input {
            margin-top: 1rem;  
            font-size:17px;
            font-weight: 600;
            padding-left: .3rem;
            color: #818181;
            text-transform: uppercase;
            border:none;
            width: 90%;
            background: transparent;
            border-bottom:1px solid #c7c7c7;
            &:focus {
                outline: none;
                border-bottom:1px solid #42e3f0;
            }

            &::placeholder {
                font-size: 15px;
                color: #c9c9c9;
            }
            @media (max-width: 290px) {
                width: 50%;
            }
        }

        .error {
            color:#e13f09;
            font-size: 1rem;
            padding-top:1rem; 
        }

        .continue {
            padding-top:2rem;            
            .button {
                cursor:pointer;
                color:white;
                text-transform:uppercase;
                justify-self: center;
                padding: 1rem;
                background-color: #21a3ad;
                box-shadow: 0px 1px 10px #999;
                &:hover {
                    background-color: #28bfcc;
                }
            }
        }        
    }

}
.success {
    text-align: center;
    margin-top: 5rem;
    color: #51aeb3;
}
.back {
    text-align: center;
    margin-top: 1rem;
    color: #2c6265; 
    cursor: pointer;
}

</style>

{#if showForm}
<div class="credit-card" transition:fade>
    <div class="card-container">
        <div class="card">
            <div class="logo-container">
                <div class="logo">
                    <img src={ logo } class="coderos" alt="Coderos">
                    {#if src !== ''}
                        <img class="company" { src } alt="company">
                    {/if}
                    
                </div>
            </div>
            <div class="chip">
                <img src={ chip } alt="chip">
            </div>
            <div class="digits">
                { #if digitsFormated !== null }
                    { digitsFormated }
                { /if }
                
            </div>
            <div class="expiration">
                <span>Válida hasta:</span> { month !== undefined ? month : ''  }/{ year !== undefined ? year : '' }
            </div>
            <div class="name">
                { name.toUpperCase() }
            </div>
        </div>
    </div>
    <div class="info">
        <h1>Ingrese datos de Tarjeta</h1>
        <div class="form">
            <div class="numberAndName">
                <input on:keyup={ formatDigits } placeholder="Número en Tarjeta" type="number" pattern="/^-?\d+\.?\d*$/" onKeyPress="if(this.value.length==16) return false;">
                <input bind:value={ name } placeholder="Nombre en Tarjeta" type="text" maxlength="25">
            </div>
            <div class="date">
                <input bind:value={ month } type="number" placeholder="Mes" min="6" max="12" pattern="[0-9]+" onKeyPress="if(this.value.length==2) return false;">
                <input bind:value={ year } type="number" placeholder="Año" min="2019" pattern="/^-?\d+\.?\d*$/" onKeyPress="if(this.value.length==4) return false;">
            </div>
        </div>
        <div class="error">
            { message }
        </div>
        <div class="continue">
            <div class="button" on:click={ add }>
                <span>agregar método de pago</span>
            </div>
        </div>
    </div>
</div>
{:else}
    {#if visible}
        <h1 transition:fade class="success">Realizado Correctamente!</h1>
        <h2 class="back" on:click={ back }>Regresar</h2>
    {/if}
{/if}
