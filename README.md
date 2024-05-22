# Full Cycle 
# Módulo - Sistemas monolíticos
# Desafio - Criação de módulo de Invoice 

Neste desafio será necessário criar o módulo completo de invoice - Nota Fiscal do Monolito.

Para este módulo você precisa utilizar:

* Os use cases de find e generate
* Especificar todas as entradas e saídas conforme o DTO exibido ao final deste enunciado.
Os campos do invoice são:

```
id?: Id // criado automaticamente
name: string
document: string
address: Address // value object
items: InvoiceItems[] // Invoice Items entity
createdAt?: Date // criada automaticamente
updatedAt?: Date // criada automaticamente
```

A entidade InvoiceItems precisa ter:

```
id?: Id // criada automaticamente
name: string
price: number
```


Para ser considerado completo, o módulo precisa ter o facade, factory, domain, gateway, repository e usecase.

```
// DTO Find
export interface FindInvoiceUseCaseInputDTO {
  id: string;
}

export interface FindInvoiceUseCaseOutputDTO {
  id: string;
  name: string;
  document: string;
  address: {
    street: string;
    number: string;
    complement: string;
    city: string;
    state: string;
    zipCode: string;
  };
  items: {
    id: string;
    name: string;
    price: number;
  }[];
  total: number;
  createdAt: Date;
}

// DTO Generate
export interface GenerateInvoiceUseCaseInputDto {
  name: string;
  document: string;
  street: string;
  number: string;
  complement: string;
  city: string;
  state: string;
  zipCode: string;
  items: {
    id: string;
    name: string;
    price: number;
  }[];
}

export interface GenerateInvoiceUseCaseOutputDto {
  id: string;
  name: string;
  document: string;
  street: string;
  number: string;
  complement: string;
  city: string;
  state: string;
  zipCode: string;
  items: {
    id: string;
    name: string;
    price: number;
  }[];
  total: number;
}
```
