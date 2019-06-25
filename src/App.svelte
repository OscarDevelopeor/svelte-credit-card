<script>
	import CreditCard from './components/creditCard.svelte';

	// let src = './assets/images/coderos.png'; NO FUNCIONA
	// let logo = 'coderos.png'; NO FUNCIONA
	let imageBase64 = 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAWlBMVEVqtrr///9ntrtis7dfsrZhsrfV6erB3+B6vcF0ur5bsLSCwcTY6uv7/f3o8/SIw8er1Nbx+PjH4uPg7/CdzdC42tyQx8rN5eaj0NKw1tiYy83u9vbl8vK93N/zuUhJAAAIK0lEQVR4nO2da3uiMBCFIYGqUbxWRd3+/7+5otu9WE4y1pMJsJxnP7VLOi+QSTKZCZnxKuuDAgg9p/vU84SpLf6GniJMbew3JSZMbegLEhGmNvJFhQlTW/iyAoSpzaPIR5jaNpIwYWrLaEKEqe0iqp0wtVVUtRGmtomsr4SpLaLrkTC1PRH0vxGmtiaK/iZMbUscDZ8w+0OY2pJYGj5h9kmY2o6IGgn7rzthaiuiaiTsvxrC1DZE1kjYf42E/dfQ+f4HwlGjRo0aNUpfxl5VFkV5kxVfd7+gKJrLbVcHaWtdkc3P9eljezwubqpL6bX3C96O28l+fV7Nrk3J746OrMvOk12VP+hdZme5e7iuWh7rqevQwyzM+scj3F0z0eXH1ms325XrxpMsZtt2vKumkgbKN3T5Zv1EX44lYz8g38uEV8Z3F5sgZN184wF8nTDPF2ljZa72GUchzKtpwjfVnfyAFMI8nydDLNYB00iE+SzRi2oPIctYhJtUDzEIyCLMj0Vslja5sGE0wnyV4D01q7BdPMJlgmHRPU4moxImeIhmLjCLSPgmXafQVE50CXN1d+q8s7UIhGdtxKnEKiah9oBhg9MZNuFG2ZuCVev3CBeitmIjPUg0VuSVqC3h+6A8XogcTSWcMQeXKDetdV2N9dlyWWz367quxUuC4lzX69N+u1h6Wp0oj4jQkI+VdUVpS2ufuOe3MOv1nytWEPJN15nCweLsXusuxiG/80PVmRq0NLwQzABNb1SfoT0DMyavuwPkxCpVT2NRBEoY5fbJoZ6oOlrAIUw0xPtVoI74etNPyO7jWQGnS6ItApYgIaGvwHUZ4f2QC4byCaMyvHu6hOg+EwaLEs3h5pqupgDbTRWBEPppVcIyJuF7FwiRv2MQwvmSLiFYljMW4jAQ2wlCxrQUxik7QUgJTaN1SycId4MnXDAIZ4Dw0AVCzjocEKqGolAAkBK2RTEg1ag3CiZuYxIS1p5yIULCEv/aBb5kj91VqxJe2o3YM4xAYQzVgCky4sSIaaLbd9IkLNpt4NxmB9IAPzQJ0ZBFcQaok2vur8Gp44HiacDCRTPoDZdwlEHZgsWnZj5G3FAKan2juDUDd20prcNgLKV1mYqogXe4ZUDp5TKh9Q1nrx36MT1nWqLXiLI8xGORXk4N3DvZcnwBmpiqzWpwwhdpbgzvoJavQbMqWtwdxZuvPVFlSHQwlYaV1AMnFNe3JL6zsRbn91BWh40M/BP5Ie5TtEVRIy+QEwMpvnyk7cyVMQI2rlF23nr4iJlncHPmpt1pZRtzqJM482N5CWZBEX156buTjarNckkdOzwd44+I99RbTPUpWrdvZEL39Ko9862R3FJtQm66ixUk82kTnrmrNxSOSkdIn23A6XciwiV9rgFXiWkIYwQYikBtoyrhJcquUKh8U5FwF2nZVvjL//QIt9Emw3bq86hqhJss3srbobCl7jPMD7EWbdZb86DpacQHYDz3RzP/ZF91tIiz9A6sZnRH/Ah77DY0b1OetU3ZQ2K4zFiZkD2r8S/zUxCyosG/FfyD+itgapIyDpkmJKRkfH0qvHZiEwr+ILNaQPII8y3Vfx/O7+v90e+/KQlRdwXu6G5yqt/fuXlut2PKCpfVngrBikbodaS7s3O34r84iXzW4T0FlZj3Jv7xWCU+TIGW0oNf0p3G0Vg4usBKB8F7T0pVlvgdIr2luBReq7gLlsiSOmLsXXSBBWhSTMqPLNEdpE/vkWDNB6mgHE1oFA+OQBlDC8qICMuCiFOKkJArYJTMeFypYqI3yjzjFJTDAkTFEkt4Uhsnrw1tj2rmCKPxgtI4Wlhw+oBQyNtR3iNYcqR59Acq+qAUX8FyFU1ClFtHmdSgKQ2lmEMqNCBSclzRBrduRQkwglONAG6fbt0TeJEo6ZeoCygmQWNnQKkKQm5Mtf4QEVKcQVRHLRU66ogTwuwEYczSJDSd0D01AtUBM/rh8Gu5O03IKLjo9pkKlFMj4LkYr7ctV9STP9DiU/WMIUQY9fSWThAyTlGCYRpdQhSVJoz4kFD1NDN0ihIjjAG31rpBSLCiCyWknnAYoa/AImPdcxORFYQVTsw+Lhd8kwjZXyh+oHy6J/J3jJR90PRF9RxhOCrnL3/2BibN8ssBvIKbpNXBld/NkjDNV+lgEcJO+dh5ZMf1Xm/rwzQrnXsiaeL+v+fn/RvOKVU+WN8JCqHyvbBTmuxShdujJnmFJTt1XlrOJvqShPKZ7KLEM+EUBx6G+q9Uw6Xi0/5FhLLPneguLTLpFzyIhLysOaHgyQ6xCNU/pSP7hAeRUHVfppHgo2tcQv1Pr5USF88jTPDlNbiAikOo7UkbWYGvoREm+XieoOaDRxgbpl2CmRuLkFwKL1fwPSURfqT6ZK4JTmw4hDonC7XKTgNPkUIYr85YIJv5vtDEIVwn/qpz6T1n5XXCyzTJR1b/VjH1lEK+Slito5yY9KzcbIK642uEl7oDn1a/qyxXk7YOKTtsoTU0We328+j1P8/IWGfn9WSx3Pz1OKXxv3/WKdVmuZjUc9spvF8yTXVbYbPZdD5fNRJ3oXLa/Pf5fD6dZWXTBq8uLVI3NndFvULaML/JjskMnnEk7L9Gwt7r6p5jeOgOaSTsvcyNcMiII2HvZX4RDhfxN+FQEc3/RDhMRDN0QvMP4RARHwiHh2iGTmi+EA4NsYVwWIimjXBIiKadcDiIBhEOBNEYTDgIxkciMzTEL0CPP+g5YwvO1x/1mLEVpu2HPUVsRQGEfYSEIOgX/YL0UXh+1wvMkP3mJ3OQXQ2WpvZjAAAAAElFTkSuQmCC';

</script>

<style lang="scss">

	* {
		box-sizing: border-box;
	}

	html, body, div, span,
	h1, h2, h3, h4, h5, h6, p, ul {
		margin: 0;
		padding: 0;
		border: 0;
		outline: 0;
		vertical-align: baseline;
	}

	body {
		background: #f8f7fc; 
		padding: 0px !important;
	}

  	.container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 20px;
	}

	.index {
		text-align: center;

		img {
			width: 10%;
		}
		h1 {
			font-size: 1.5rem;
		}
		h2 {
			font-size: 1rem;
		}
	}
	

</style>

	<body>
		<div class="container">
			<!-- <img {src}> NO FUNCIONA SIN ERROR EN CONSOLA -->
			<!-- <img src="./assets/images/coderos.png" alt=""> NO FUNCIONA SIN ERROR EN CONSOLA  -->
			<!-- <img src="./coderos.png" alt=""> NO FUNCIONA SIN ERROR EN CONSOLA  -->
			<!-- <img src={logo}> NO FUNCIONA SIN ERROR EN CONSOLA  -->
			<div class="index">
				<img class="logo" src={imageBase64} alt="">
				<h1>Reto Coderos Junio</h1>		
				<h2>Oscar Developeor</h2>		
			</div>
			<CreditCard logo={imageBase64}/>
		</div>
	</body>
