# TheCatAPI

>
> The Cat API é uma API pública de gerenciamento de informações e imagens de gatos que usaremos no nosso curso **Decolando em TW**.
> 
> Para observar a API em funcionamento, consulte a [coleção do Postman](https://www.postman.com/winter-shuttle-98074/workspace/thecatapi/collection/22116190-45a163ae-36c7-4fbc-add6-eae0011333c5?action=share&creator=22116190).
>


## Obter a API key

Registre-se em [https://thecatapi.com/signup](https://thecatapi.com/signup) para receber sua API key por email. A API key deve ser informada no header das chamadas através da variável `x-api-key`.

O path a ser utilizado nas chamadas é o [https://api.thecatapi.com/v1](https://api.thecatapi.com/v1).

## Images

O objeto `images` representa as fotos de gatos enviadas. Imagens que não contiverem gatos ou forem inapropriadas são rejeitadas.

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
| `id` | ID da imagem. | `UUID` | Sim |
| `url` | URL para acessar a imagem. | `string` | Sim |
| `width` | Largura da imagem em pixels. Automaticamente gerada. | `integer` | Sim |
| `height` | Altura da imagem em pixels. Automaticamente gerada. | `integer` | Sim |
| `sub_id` | ID para identificação interna. | `string` | Não |
| `created_at` | Data de upload da imagem no formato *2022-11-24T17:41:35.000Z* | `datetime` | Sim | 
| `original_filename` | Nome do arquivo original. | `string` | Sim | 
| `pending` | Flag interna de ciclo de vida. 0=falso, 1=verdadeiro | `integer` | Não | 
| `approved` | Flag interna de ciclo de vida. 0=falso, 1=verdadeiro | `integer` | Não | 
| `breed_ids` | **Não implementado.** | N/A | Não | 

### POST

**Endpoint:** `POST /images/upload`

Cria uma nova imagem no sistema carregando um arquivo .jpg ou .png válido contendo um gato.

**Request body**

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
| `file` | Arquivo em PNG or JPG. | `file` | Sim |
| `sub_id` | ID para identificação interna. | `string` | Não |

**Response**

| Código | Descrição |
|------|-----------|
| 201 | Image was successsfully uploaded. |    
| 400 | Image was too big, did not contain a Cat, was inappropriate, or the wrong file type. |

### GET by ID

**Endpoint:** `GET /images/{image_id}`

Obtém a imagem correspondente ao parâmetro `image_id` passado como parâmetro `path`.

### GET

**Endpoint:** `GET /images`

Obtenha todas as imagens enviadas para sua conta via '/images/upload'.

Por esse endpo

     Liste suas imagens, uma paginação através delas usando o parâmetro ‘page’ e o cabeçalho de resposta ‘pagination-count’
     filtre as imagens para retornar apenas aquelas enviadas por um de seus usuários usando o parâmetro 'sub_id'.
     veja se uma imagem já existe antes de fazer o upload usando o parâmetro 'original_filename' para procurar uma correspondência.

**Parâmetros query**:

| Parâmetro |    Descrição      | Obrigatório |
|:------------:|:--------------------:|-------------|
| `limit`  | Integer - number of results to return. Without an API Key you can only pass 1, with a Key you can pass up to 25. Default is 1  | Sim |
| `size`  | The size of image to return - small, med or full. small is perfect for Discord. Defaults to med  |  Não |
| `mime_types` | Comma delimited string of the image types to return gif, jpg, orpng. Defaults to return all types jpg,gif,png.      |   Não   |
| `format` | Response format json, orsrc. src  will redirect straight to the image, so is useful for putting a link  straight into HTML as the 'src' on an 'img' tag. Defaults to json     |  Não   |
| `order` | The order to return results in. RANDOM, ASC or DESC. If either ASC or DESC  is passed then the Pagination headers will be on the response allowing  you to see the total amount of results, and your current page. Default  is RANDOM |  Não    |
| `page` | Integer - used for Paginating through all the results. Only used when order is ASC or DESC        |   Não  |

**Paginação**

If order=ASC or order=DESC is passed, then the response will contain these values as Headers.

|    Parâmetro     |                         Descrição                  | Tipo |
|:----------------:|:--------------------------------------------------:|---|
| `Pagination-Count` | The total amount of results matching your search | `integer` |
| `Pagination-Page`  | The current page                                 | `integer` |
| `Pagination-Limit` | Amount of results being returned per page        | `integer` |

### DELETE

**Endpoint:** `DELETE /images/{image_id}`

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |

**Response**
