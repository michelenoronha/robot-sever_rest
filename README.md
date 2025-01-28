 ROBOT WITH SELENIUM

The Robot Framework is a versatile, open-source automation framework for acceptance testing, acceptance test-driven development (ATDD), and robotic process automation (RPA). It allows you to write test cases in a readable, easy-to-understand format.

To test APIs with Robot Framework, you can use the "RequestsLibrary" library, which provides keywords for making HTTP requests. Here's a brief overview of how you can test APIs using Robot Framework:

1. **Installation:**
   First, you need to install the `robotframework-requests` library. You can do this using pip:
   ```
   pip install robotframework-requests
   ```

2. **Importing the Library:**
   In your Robot Framework test suite or test case file, import the `RequestsLibrary`:

   ```robot
   *** Settings ***
   Library  RequestsLibrary
   ```

3. **Writing Test Cases:**
   Create test cases that involve making HTTP requests. Use keywords provided by the `RequestsLibrary` to interact with APIs. For example:

   ```robot
   *** Test Cases ***
   Get Weather Forecast
       Create Session  WeatherAPI  https://api.weatherapi.com
       ${response}  Get Request  WeatherAPI  /forecast.json  params={'key': 'your_api_key', 'q': 'city_name'}
       Should Be Equal As Numbers  ${response.status_code}  200
   ```

   In this example, the test case creates a session with the WeatherAPI, makes a GET request to retrieve the weather forecast, and then checks if the status code is 200.

4. **Handling Responses:**
   You can extract and verify information from API responses using Robot Framework's built-in keywords. For instance, you might use the `Should Be Equal As Strings` keyword to compare expected and actual response data.

   ```robot
   *** Test Cases ***
   Verify Temperature
       ${temperature}  Set Variable  ${response.json()['current']['temp_c']}
       Should Be Equal As Strings  ${temperature}  25
   ```

   This example extracts the current temperature from the API response and checks if it's equal to the expected value.

5. **Clean Up:**
   Remember to close the session after testing:

   ```robot
   *** Test Cases ***
   Cleanup
       Delete All Sessions
   ```

   This ensures that resources are properly released.

6. **Run Tests:**
   Execute your tests using the `robot` command:

   ```
   robot your_test_file.robot
   ```

# Robot-Sever_Rest com Selenium

Test API com Robot Framework e Selenium

O Robot Framework é um framework de automação de código aberto e versátil, usado para testes de aceitação, desenvolvimento orientado por testes de aceitação (ATDD) e automação de processos robóticos (RPA). Ele permite que você escreva casos de teste em um formato legível e fácil de entender.

Para testar APIs com o Robot Framework, você pode usar a biblioteca "RequestsLibrary", que fornece palavras-chave para fazer solicitações HTTP. Aqui está uma breve visão de como você pode testar APIs usando o Robot Framework:

1. **Instalação:**
   Primeiro, é necessário instalar a biblioteca `robotframework-requests`. Você pode fazer isso usando o pip:
   ```
   pip install robotframework-requests
   ```

2. **Importando a Biblioteca:**
   Em seu conjunto de testes ou arquivo de caso de teste do Robot Framework, importe a `RequestsLibrary`:
   ```robot
   *** Configurações ***
   Biblioteca  RequestsLibrary
   ```

3. **Escrevendo Casos de Teste:**
   Crie casos de teste que envolvam fazer solicitações HTTP. Use palavras-chave fornecidas pela `RequestsLibrary` para interagir com APIs. Por exemplo:
   ```robot
   *** Casos de Teste ***
   Obter Previsão do Tempo
       Criar Sessão  WeatherAPI  https://api.weatherapi.com
       ${resposta}  Obter Solicitação  WeatherAPI  /forecast.json  params={'key': 'sua_chave_api', 'q': 'nome_da_cidade'}
       Deve Ser Igual A Números  ${resposta.status_code}  200
   ```

4. **Manuseio de Respostas:**
   Você pode extrair e verificar informações das respostas da API usando as palavras-chave integradas do Robot Framework. Por exemplo, você pode usar a palavra-chave `Deve Ser Igual Como Strings` para comparar dados de resposta esperados e reais.
   ```robot
   *** Casos de Teste ***
   Verificar Temperatura
       ${temperatura}  Definir Variável  ${resposta.json()['current']['temp_c']}
       Deve Ser Igual Como Strings  ${temperatura}  25
   ```

5. **Limpeza:**
   Lembre-se de fechar a sessão após os testes:
   ```robot
   *** Casos de Teste ***
   Limpeza
       Excluir Todas as Sessões
   ```

   Isso garante que os recursos sejam liberados adequadamente.

6. **Executar Testes:**
   Execute seus testes usando o comando `robot`:
   ```
   robot seu_arquivo_de_teste.robot
   ```




That's a basic overview of testing APIs with Robot Framework. It provides a clear and readable syntax for API testing and integrates well with other libraries and tools.
