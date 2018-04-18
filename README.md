# PROXI Schemas

The [HUPO-PSI Consortium](http://www.psidev.info/) defines community standards for data representation in
proteomics to facilitate data comparision, exchange and verification.

The **PRO**teome**X**change expression **I**nterface is a suite of integrated APIs each targeting a different aspect
of exchanging proteomics information between ProteomeXchange data partners and consumers.

## Structure of the Repository

- Schemas : Contains the **OpenAPI** definition of the Object schemas divided by categories:
  - dataset: ProteomeXhange **Dataset** definition including additional information such as **Contact**
  - common: Containing the Common data structures for the schemas such as **OntologyTerm**
  - biology: The biology folder contains data structure to identified molecules such as **Proteins**,  **Peptides**

The api-swagger.yaml file contains the current definition of the API. For convenience and simplicity all the definitions on the
schemas folder are duplicated in the api-swagger.yaml file.

> The first implementation of the PROXI _v1_ will be focus only on retriving data from public repositories
> using **GET** methods.

## API standard (OpenAPI)

The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs which allows both humans
and computers to discover and understand the capabilities of the service without access to source code, documentation,
or through network traffic inspection. When properly defined, a consumer can understand and interact with the remote
service with a minimal amount of implementation logic.

[Read More](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md)

## PROXI Specification version _v1_:

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",
"NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described
in [BCP 14](https://tools.ietf.org/html/bcp14) [RFC2119](https://tools.ietf.org/html/rfc2119)
[RFC8174](https://tools.ietf.org/html/rfc8174) when, and only when, they appear in all capitals,
as shown here.

### Naming conventions

- A **resource** SHOULD be represented as a collection. For example, “datasets” is a collection of datasets
where we can identify a single “dataset” using the resource URI “/datasets/{customerId}”.

- SHOULD NOT use trailing forward slash (/) in URIs:

```
  http://api.example.com/device-management/managed-devices/
  http://api.example.com/device-management/managed-devices 	/*This is much better version*/

```

- SHOULD NOT use underscores ( _ ), instead use ( - ):

It’s posible to use an underscore in place of hyphen to be used as seperator – But depending on the application’s font,
it’s possible that the underscore (_) character can either get partially obscured or completely hidden in some browsers
or screens.

To avoid this confusion, use hyphens (-) instead of underscores ( _ ).

```
http://api.example.com/inventory-management/managed-entities/{id}/install-script-location  //More readable
http://api.example.com/inventory_management/managed_entities/{id}/install_script_location  //More error prone
```



### Install the swagger generation

```bash
> wget http://central.maven.org/maven2/io/swagger/swagger-codegen-cli/2.3.1/swagger-codegen-cli-2.3.1.jar -O swagger-codegen-cli.jar
```




