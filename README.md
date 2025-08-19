# GHERKIN
Repositorio para definir casos de prueba en gherkin

# GHERKIN

Gherkin es un lenguaje específico de dominio (DSL) diseñado para describir casos de prueba de manera legible.  
Se utiliza principalmente en herramientas como Cucumber para pruebas basadas en comportamiento (BDD).  
Gherkin usa una sintaxis simple con palabras clave como `Feature`, `Scenario`, `Given`, `When`, `Then`, `And`, y `But` para estructurar los casos de prueba.

## Explicación de las palabras clave en Gherkin:

- **Feature**: Describe la funcionalidad principal que estás probando (en este caso, el login de usuario).
- **Scenario**: Representa un caso específico dentro de la funcionalidad (en este caso, un login exitoso).
- **Given**: Define el estado inicial o precondiciones (el usuario está en la página de login).
- **When**: Describe la acción que se realiza (el usuario ingresa credenciales válidas y hace clic en el botón de login).
- **Then**: Define el resultado esperado (el usuario es redirigido al dashboard).

## Ejemplo básico:

```gherkin
Feature: Inicio de sesión  // Descripción de la funcionalidad de inicio de sesión

  Scenario: Inicio de sesión exitoso // Caso de prueba y pasos 
    Given el usuario está en la página de inicio de sesión
    When el usuario ingresa credenciales válidas
    And hace clic en el botón de iniciar sesión
    Then el usuario debería ser redirigido al panel principal

  Scenario: Inicio de sesión fallido con datos inválidos
    Given el usuario está en la página de inicio de sesión
    When el usuario ingresa credenciales inválidas
    And hace clic en el botón de iniciar sesión
    Then el usuario debería ver un mensaje de error indicando "Credenciales inválidas"

  Scenario: Inicio de sesión fallido con campos en blanco
    Given el usuario está en la página de inicio de sesión
    When el usuario deja los campos de usuario y contraseña en blanco
    And hace clic en el botón de iniciar sesión
    Then el usuario debería ver un mensaje de error indicando "Los campos no pueden estar vacíos"
