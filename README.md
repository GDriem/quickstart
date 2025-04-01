# Implementación del Protocolo Client Credentials con Duende IdentityServer

Este proyecto es una implementación práctica del flujo de **Client Credentials** utilizando **Duende IdentityServer**. El objetivo es demostrar cómo configurar un servidor de identidad, una API protegida y un cliente que accede a dicha API utilizando tokens de acceso.

## Estructura del Proyecto

La solución consta de tres proyectos principales:

1. **IdentityServer**: Actúa como el proveedor de identidad y emite tokens de acceso a los clientes autenticados.
2. **Api**: Una API protegida que requiere un token válido para acceder a sus recursos.
3. **Client**: Una aplicación cliente que solicita tokens de acceso a `IdentityServer` y utiliza esos tokens para acceder a la `Api`.

## Tecnologías Utilizadas

- **.NET 9.0**
- **Duende IdentityServer 7**
- **ASP.NET Core**
- **IdentityModel 7**

## Configuración y Ejecución

### Prerrequisitos

- **.NET SDK 9.0** o superior instalado.
- Certificados HTTPS de desarrollo confiables:

    ```bash
    dotnet dev-certs https --trust
    ```

### Pasos para Ejecutar la Solución

1. **Clonar el Repositorio**

    ```bash
    git clone https://github.com/GDriem/quickstart.git
    cd quickstart
    ```

2. **Restaurar y Compilar**

    ```bash
    dotnet restore
    dotnet build
    ```

3. **Ejecutar los Proyectos**

    Desde tres terminales distintas:

    ```bash
    cd src/IdentityServer
    dotnet run
    ```

    ```bash
    cd src/Api
    dotnet run
    ```

    ```bash
    cd src/Client
    dotnet run
    ```

4. **Verificar Funcionamiento**

    - El cliente obtendrá un token desde `IdentityServer`.
    - Luego lo usará para hacer una solicitud autenticada a la API.
    - La respuesta de la API se mostrará en la consola.

## Enlace de referencia

Guía oficial usada como base para este proyecto:  
👉 [https://docs.duendesoftware.com/identityserver/v7/quickstarts/1_client_credentials/](https://docs.duendesoftware.com/identityserver/v7/quickstarts/1_client_credentials/)
