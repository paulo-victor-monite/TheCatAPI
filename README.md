# TheCatAPI

>
> Decolando em TW
>

[https://docs.thecatapi.com/](https://docs.thecatapi.com/)

## Obter a API key

Registre-se em [https://thecatapi.com/signup](https://thecatapi.com/signup) para receber sua API key por email.

## Visão geral

Esse recurso funciona como um banco de dados de imagens de gatos.

## Obter todas imagens públicas

Para obter uma lista de todas as imagens públicas criadas, chame `GET /images/search`.


```cURL
curl GET 'https://api.thecatapi.com/v1/images/search'
```

A resposta contém as informações sobre todas imagens públicas criadas:
```json
[
    {
        "id": "Fvdx5Ja0F",
        "url": "https://cdn2.thecatapi.com/images/Fvdx5Ja0F.jpg",
        "width": 600,
        "height": 450
    }
]
```

Você pode classificar os produtos por nome e filtrá-los por nome, preço, unidade de medida e outros campos. Para obter uma lista completa dos parâmetros de classificação e filtro disponíveis, consulte a descrição do ponto de extremidade GET /products.
