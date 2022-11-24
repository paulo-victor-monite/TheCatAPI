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

**Endpoint: **`GET /images/{image_id}`
Obtém a imagem correspondente ao parâmetro `image_id` passado como parâmetro `path`.

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |

**Response**

### GET
`GET /images`

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |

**Response**

### DELETE
`DELETE /images/{image_id}`

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |

**Response**
