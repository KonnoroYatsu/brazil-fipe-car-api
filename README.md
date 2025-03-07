[🇧🇷 Versão em Português](#ptbr-begin-section-anchor)
<br/>
[🇺🇸 English Version](#en-begin-section-anchor)

# Brazil Fipe Car API - (Seção Portugues) <a name="ptbr-begin-section-anchor"></a>

## Descrição

A **Brazil Fipe Car API** é um serviço desenvolvido para facilitar a consulta do valor de tabela FIPE de um veículo. Utilizando a API **parallelum.com.br**, esta API realiza automaticamente as requisições necessárias para obter os valores da tabela FIPE com base nas informações fornecidas pelo usuário.

## Como Funciona

A API **parallelum.com.br** exige quatro chamadas para obter o valor da tabela FIPE de um carro. A ordem das chamadas é a seguinte:

1. **Obter as marcas de carros disponíveis:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas`
2. **Obter os modelos disponíveis para a marca especificada:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos`
3. **Obter os anos disponíveis para o modelo especificado:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos/{modeloId}/anos`
4. **Obter os dados da tabela FIPE para o modelo especificado:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos/{modeloId}/anos/{anoId}`

Cada chamada depende da resposta da anterior, pois os identificadores retornados são necessários para a próxima requisição.

## Endpoints da API

A **Brazil Fipe Car API** disponibiliza um endpoint que automatiza todas as chamadas necessárias para obter os dados da tabela FIPE.

### **Obter o valor FIPE de um veículo**

**Requisição:**

```
GET http://localhost:8081/car-fipe
```

**Parâmetros:**

| Parâmetro    | Tipo   | Obrigatório | Descrição               |
| ------------ | ------ | ----------- | ----------------------- |
| `brand`      | String | Sim         | Nome da marca do carro  |
| `year`       | String | Sim         | Ano do modelo do carro  |
| `carDetails` | String | Sim         | Nome do modelo do carro |

**Resposta Exemplo:**

```json
[
    {
        "TipoVeiculo": 1,
        "Valor": "R$ 23.544,00",
        "Marca": "Honda",
        "Modelo": "Civic Sedan LX 1.7 16V 115cv Mec. 4p",
        "AnoModelo": 2005,
        "Combustivel": "Gasolina",
        "CodigoFipe": "014036-8",
        "MesReferencia": "março de 2025",
        "SiglaCombustivel": "G"
    },
    {
        "TipoVeiculo": 1,
        "Valor": "R$ 25.766,00",
        "Marca": "Honda",
        "Modelo": "Civic Sedan LX/LXL 1.7 16V 115cv Aut. 4p",
        "AnoModelo": 2005,
        "Combustivel": "Gasolina",
        "CodigoFipe": "014035-0",
        "MesReferencia": "março de 2025",
        "SiglaCombustivel": "G"
    }
]
```

## Como Executar o Projeto

1. Clone este repositório:
   ```
   git clone https://github.com/seu-usuario/brazil-fipe-car-api.git
   ```
2. Importe o projeto no **Anypoint Studio**.
3. Execute a aplicação dentro do Anypoint Studio.
4. Utilize uma ferramenta como **Postman**, **Insomnia**, **Hoppscotch** ou até mesmo o próprio navegador para realizar as requisições ao endpoint passando os devidos parâmetros:
   ```
   http://localhost:8081/car-fipe?brand=Honda&year=2005&carDetails=Civic
   ```

## Tecnologias Utilizadas

- **MuleSoft** para desenvolvimento da API

## Contribuição

Contribuições são bem-vindas! Para sugerir melhorias ou corrigir problemas, abra uma issue ou envie um pull request.

## Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
<br/><br/><br/>
# Brazil Fipe Car API - (English Section) <a name="en-begin-section-anchor"></a>

## Description

The **Brazil Fipe Car API** is a service developed to facilitate retrieving a vehicle’s FIPE table value. Using the **parallelum.com.br** API, this API automatically makes the necessary requests to obtain FIPE table values based on the user-provided information.

## How It Works

The **parallelum.com.br** API requires four requests to obtain the FIPE table value of a car. The order of requests is as follows:

1. **Get available car brands:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas`
2. **Get available models for the specified brand:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos`
3. **Get available years for the specified model:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos/{modeloId}/anos`
4. **Get FIPE table data for the specified model:**
   - `GET https://parallelum.com.br/fipe/api/v1/carros/marcas/{marcaId}/modelos/{modeloId}/anos/{anoId}`

Each request depends on the response of the previous one, as the returned identifiers are required for the next request.

## API Endpoints

The **Brazil Fipe Car API** provides an endpoint that automates all the necessary requests to obtain FIPE table data.

### **Get FIPE value for a vehicle**

**Request:**

```
GET http://localhost:8081/car-fipe
```

**Parameters:**

| Parameter     | Type   | Required | Description          |
| ------------ | ------ | -------- | -------------------- |
| `brand`      | String | Yes      | Car brand name      |
| `year`       | String | Yes      | Car model year      |
| `carDetails` | String | Yes      | Car model name      |

**Example Response:**

```json
[
    {
        "TipoVeiculo": 1,
        "Valor": "R$ 23.544,00",
        "Marca": "Honda",
        "Modelo": "Civic Sedan LX 1.7 16V 115cv Mec. 4p",
        "AnoModelo": 2005,
        "Combustivel": "Gasoline",
        "CodigoFipe": "014036-8",
        "MesReferencia": "March 2025",
        "SiglaCombustivel": "G"
    },
    {
        "TipoVeiculo": 1,
        "Valor": "R$ 25.766,00",
        "Marca": "Honda",
        "Modelo": "Civic Sedan LX/LXL 1.7 16V 115cv Aut. 4p",
        "AnoModelo": 2005,
        "Combustivel": "Gasoline",
        "CodigoFipe": "014035-0",
        "MesReferencia": "March 2025",
        "SiglaCombustivel": "G"
    }
]
```

## How to Run the Project

1. Clone this repository:
   ```
   git clone https://github.com/your-user/brazil-fipe-car-api.git
   ```
2. Import the project into **Anypoint Studio**.
3. Run the application inside Anypoint Studio.
4. Use a tool like **Postman**, **Insomnia**, **Hoppscotch**, or even your web browser to make requests to the endpoint with the appropriate parameters:
   ```
   http://localhost:8081/car-fipe?brand=Honda&year=2005&carDetails=Civic
   ```

## Technologies Used

- **MuleSoft** for API development

## Contributing

Contributions are welcome! To suggest improvements or fix issues, open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
