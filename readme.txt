



CircleCI tutorial
-----------------

	algemeen
		
		- we hebben een simpel script gemaakt
		- met een unit test

		- hiervoor hebben we npm gebruikt
		- zodat we Jest kunnen gebruiken voor de tests


	unit testing

		instructies opzetten npm project:

			- "npm init" --> wizard volgen:
				- 'jest' meegeven bij 'test command'

			- "npm install --save-dev jest"
				- saved Jest alleen voor dev

		instructies voor jest:

			https://jestjs.io/docs/getting-started

			- niet vergeten om de te-testen module te exporteren: "module.exports = <functie naam>;"
			- noem de test-file: '<naam van het te-testen script>.test.js'
			- voorbeeld unit-test:

				const sum = require('./sum');

				test('adds 1 + 2 to equal 3', () => {
					expect(sum(1, 2)).toBe(3);
				});
			- checken of dit ...
				"scripts": {
					"test": "jest"
				}
				... in de package.json staat
			- test runnen: "npm test"


	git project

		- git project maken:		"git init"


		- linken aan Github:

			optie 1) nieuwe repo in github en dan lokaal clonen

			optie 2) lokale repo linken aan github repo
				
				"git remote add origin https://github.com/KoenVanKesteren/circleCITutorial.git"

		- pushen naar github:		"git push origin master"


	circelCI

		tutorial: https://www.youtube.com/watch?v=0OjEx2UzLUI&list=PLRqwX-V7Uu6bLqwFa52YGEHy-L1-D_Ve-&index=4&ab_channel=TheCodingTrain

		- de config.yml
			- moet in een folder met de naam '.circleci'
			- jobs:
				"
					jobs:
						build:
							docker:
							- image: circleci/node:<node versie>

							steps:
								- checkout
								- run: <uit te voeren stap 1>
								- run: <uit te voeren stap 2>
								- run: <uit te voeren stap 3>
				"

			- 1e step moet zijn:  "checkout"	 ( ! DUS NIET "- run: checkout")