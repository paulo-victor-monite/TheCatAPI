# TheCatAPI

>
> The Cat API é uma API pública de gerenciamento de informações e imagens de gatos que usaremos no nosso curso **Decolando em TW**.
> 
> Para observar a API em funcionamento, consulte a [coleção do Postman](https://www.postman.com/winter-shuttle-98074/workspace/thecatapi/collection/22116190-45a163ae-36c7-4fbc-add6-eae0011333c5?action=share&creator=22116190).
>


## Obter a API key

Registre-se em [https://thecatapi.com/signup](https://thecatapi.com/signup) para receber sua API key por email.

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
| `breed_ids` | **Não implementado.** | N/A | Não | 

### POST
`POST /images/upload`

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
| file |           |      |             |
|      |           |      |             |
|      |           |      |             |

### GET

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |

### DELETE

| Nome | Descrição | Tipo | Obrigatório |
|------|-----------|------|-------------|
|      |           |      |             |
|      |           |      |             |
|      |           |      |             |
