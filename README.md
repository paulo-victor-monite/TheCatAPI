# TheCatAPI

>
> The Cat API é uma API pública de gerenciamento de informações e imagens de gatos que usaremos no nosso curso **Decolando em TW**.
> 
> Para observar a API em funcionamento, consulte a [coleção do Postman](https://www.postman.com/winter-shuttle-98074/workspace/thecatapi/collection/22116190-45a163ae-36c7-4fbc-add6-eae0011333c5?action=share&creator=22116190).
>


## Obter a API key

- Registre-se em [https://thecatapi.com/signup](https://thecatapi.com/signup) para receber sua API key por email.
- A API key deve ser informada no header das chamadas através da variável `x-api-key`.
- O path a ser utilizado nas chamadas é o [https://api.thecatapi.com/v1](https://api.thecatapi.com/v1).

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

### GET by ID

**Endpoint:** `GET /images/{image_id}`

Obtém a imagem correspondente ao parâmetro `image_id` passado como parâmetro `path`.

### GET

**Endpoint:** `GET /images`

Obtenha todas as imagens enviadas para sua conta via '/images/upload'. Os resultados podem ser filtrados através dos parâmteros `query` abaixo:

| Parâmetro |    Descrição      | Tipo | Obrigatório |
|------------|--------------------|------|------------|
| `limit`  | Número de resultados a serem retornados. O valor máximo é 25. O padrão é 1. | `integer` | Sim |
| `mime_types` | The image types to return: `gif`, `jpg`, or `png`. Retorna todos os tipos como padrão. | `string` delimitado por vírgulas | Não |
| `order` | The order to return results in. RANDOM, ASC or DESC. If either ASC or DESC  is passed then the Pagination headers will be on the response allowing  you to see the total amount of results, and your current page. Default  is RANDOM | `string` | Não  |

### DELETE

**Endpoint:** `DELETE /images/{image_id}`

Exclui a imagem correspondente ao parâmetro `image_id` passado como parâmetro `path`.
