1º) Instalar o Expo no PC de forma global
	npm install expo -g cli
	
2º) Criar o projeto via Expo
	expo init mobile
	Isso vai criar o diretorio com o nome *mobile* com os recursos do Expo no projeto
	
3º) Execução do Projeto:
	#Usar o comando para iniciar a execução necessita do módulo yarn global#
	yarn start
	
	No celular, instalar o app EXPO <- Disponível nas lojas
	No Emulador, configurar o emulador para reconhecer a aplicação
	
4º) Ajustar o ícone do app e Splash screen
	Criar o ícone e aplicar o nome: icon.png <- Colocar dentro de ./assets (raiz)
	Criar a Splash Screen com o nome: splash.png <- Colocar dentro de ./assets
	
5º Configurar a navegação:
	Toda configuração de estrutura de pastas e inicialização é igual ao React
	Usar a biblioteca React-Navigation: http://reactnavigation.org/docs/getting-started
	instalar a biblioteca:
		npm install @react-navigation/native
	Instalar as dependências do react-navigation/native:
		expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view
		
	As navegações podem ser feitas de diversas formas. Formatos de navegação: http://reactnavigation.org/docs/hello-react-navigation
	
	Navegação padrão através de pilhas:
		npm install @react-navigation/stack
		
6º) Criar as importações dentro do routes.js :
	import { NavigationContainer } from '@react-navigation/native';
	import { createStackNavigator } from '@react-navigation/stack';

	const AppStack = createStackNavigator();

	import Incidents from './pages/Incidents';
	import Detail from './pages/Detail';

	export default function Routes(){
		return(
			<NavigationContainer>
				<AppStack.Navigator>
					<AppStack.Screen component={Incidents} />
					<AppStack.Screen component={Detail} />
				</AppStack.Navigator>
			</NavigationContainer>
		);
	}
	
7º) Importar as Rotas do arquivo routes.js no arquivo App.js:

	