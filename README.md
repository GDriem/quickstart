# Implementación del Protocolo Client Credentials con Duende IdentityServer

Este proyecto es una implementación práctica del flujo de **Client Credentials** utilizando **Duende IdentityServer**. El objetivo es demostrar cómo configurar un servidor de identidad, una API protegida y un cliente que accede a dicha API utilizando tokens de acceso.

## Estructura del Proyecto

La solución consta de tres proyectos principales:

1. **IdentityServer**: Actúa como el proveedor de identidad y emite tokens de acceso a los clientes autenticados.
2. **Api**: Una API protegida que requiere un token válido para acceder a sus recursos.
3. **Client**: Una aplicación cliente que solicita tokens de acceso a `IdentityServer` y utiliza esos tokens para acceder a la `Api`.

## Tecnologías Utilizadas

- **.NET 9.0**: Plataforma principal de desarrollo.
- **Duende IdentityServer 7**: Framework para la implementación de servidores de identidad y acceso.
- **ASP.NET Core**: Utilizado para construir tanto la API como el cliente.

## Configuración y Ejecución

### Prerrequisitos

- **.NET SDK 9.0** o superior instalado en tu máquina.
- **Certificados de desarrollo HTTPS** confiables. Puedes generarlos y confiarlos ejecutando:

    ```bash
    dotnet dev-certs https --trust
    ```

### Pasos para Ejecutar la Solución

1. **Clonar el Repositorio**

    ```bash
    git clone https://github.com/tu_usuario/tu_repositorio.git
    cd tu_repositorio
    ```

2. **Restaurar Paquetes y Compilar la Solución**

    ```bash
    dotnet restore
    dotnet build
    ```

3. **Ejecutar los Proyectos**

    Abre tres terminales separadas y navega a las carpetas de cada proyecto (`IdentityServer`, `Api`, `Client`). En cada terminal, ejecuta:

    ```bash
    dotnet run
    ```

    Asegúrate de que cada proyecto se esté ejecutando en los siguientes puertos:

    - **IdentityServer**: https://localhost:5001
    - **Api**: https://localhost:6001
    - **Client**: Aplicación de consola que se ejecuta localmente.

4. **Verificar la Comunicación**

    - **IdentityServer** debería mostrar que está escuchando en `https://localhost:5001`.
    - **Api** debería estar protegida y requerir un token válido para acceder.
    - **Client** debería obtener un token de `IdentityServer` y usarlo para acceder a la `Api`, mostrando la respuesta en la consola.

## Notas Adicionales

- Asegúrate de que los puertos configurados en cada proyecto coincidan con los mencionados anteriormente. Puedes ajustar los puertos en los archivos `launchSettings.json` de cada proyecto si es necesario.
- Para más detalles sobre la implementación y configuración, consulta el [quickstart oficial de Duende IdentityServer sobre Client Credentials](https://docs.duendesoftware.com/identityserver/v7/quickstarts/1_client_credentials/).
