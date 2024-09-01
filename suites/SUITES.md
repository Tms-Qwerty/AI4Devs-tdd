# Suites de Pruebas para el Sistema de Seguimiento de Talento

## 1. Suite de pruebas para el servicio de candidatos (candidateService)

Historia de usuario:
Como reclutador, quiero poder añadir nuevos candidatos al sistema con toda su información relevante, incluyendo datos personales, educación, experiencia laboral y CV, para poder gestionar eficientemente el proceso de reclutamiento.

Criterios de aceptación:

1. Se debe poder crear un nuevo candidato con datos válidos.
2. No se debe poder crear un candidato con un correo electrónico que ya existe en la base de datos.
3. Se deben validar todos los campos obligatorios antes de crear un candidato.
4. Se debe poder añadir múltiples registros de educación para un candidato.
5. Se debe poder añadir múltiples experiencias laborales para un candidato.
6. Se debe poder añadir un CV al candidato.
7. No se debe poder crear un candidato con un correo electrónico inválido.
8. No se debe poder crear un candidato con fechas de educación o experiencia laboral inválidas (por ejemplo, fecha de fin anterior a la fecha de inicio).
9. No se debe poder crear un candidato con un número de teléfono inválido.
10. No se debe poder crear un candidato con un CV que tenga un tipo de archivo no permitido.

## 2. Suite de pruebas para el controlador de candidatos (candidateController)

Historia de usuario:
Como reclutador, quiero poder interactuar con la API para añadir nuevos candidatos al sistema, de manera que pueda gestionar eficientemente el proceso de reclutamiento a través de una interfaz REST.

Criterios de aceptación:

1. El controlador debe poder recibir una solicitud POST con los datos del candidato y procesarla correctamente.
2. Si los datos del candidato son válidos, el controlador debe responder con un código de estado 201 y los datos del candidato creado.
3. Si los datos del candidato son inválidos, el controlador debe responder con un código de estado 400 y un mensaje de error apropiado.
4. El controlador debe manejar errores inesperados y responder con un código de estado 500 en caso de que ocurran.
5. El controlador debe manejar correctamente una solicitud POST con un cuerpo vacío.
6. El controlador debe manejar correctamente una solicitud POST con datos parciales (faltando campos obligatorios).
7. El controlador debe manejar correctamente una solicitud POST con un tipo de contenido incorrecto.

## 3. Suite de pruebas para el modelo de Candidate

Historia de usuario:
Como desarrollador del sistema, quiero asegurarme de que el modelo de Candidate funcione correctamente para guardar y recuperar datos de candidatos de la base de datos, de manera que pueda confiar en la integridad y consistencia de los datos almacenados.

Criterios de aceptación:

1. Se debe poder crear una nueva instancia de Candidate con datos válidos.
2. El método save() debe guardar correctamente un nuevo candidato en la base de datos.
3. El método save() debe actualizar correctamente un candidato existente en la base de datos.
4. El método findOne() debe recuperar correctamente un candidato existente de la base de datos.
5. Se deben manejar correctamente los errores de base de datos, como violaciones de restricciones únicas.
6. No se debe poder guardar un candidato con un email que ya existe en la base de datos.
7. No se debe poder actualizar un candidato que no existe en la base de datos.
8. Se debe poder guardar un candidato con un número grande de registros de educación o experiencias laborales.

## 4. Suite de pruebas para la validación de datos de candidatos

Historia de usuario:
Como reclutador, quiero asegurarme de que los datos ingresados para los candidatos sean válidos y cumplan con los requisitos establecidos, de manera que pueda mantener la calidad y consistencia de la información en el sistema.

Criterios de aceptación:

1. La función validateCandidateData() debe validar correctamente todos los campos obligatorios del candidato.
2. Se debe validar que el nombre y apellido del candidato contengan solo caracteres alfabéticos y espacios.
3. Se debe validar que el email del candidato tenga un formato válido.
4. Se debe validar que el número de teléfono del candidato tenga un formato válido (si se proporciona).
5. Se deben validar las fechas de educación y experiencia laboral para asegurar que tengan un formato válido.
6. Se debe validar que la información del CV (si se proporciona) contenga una ruta de archivo y un tipo de archivo válidos.
7. La función debe lanzar errores específicos para cada tipo de validación fallida.
8. Se deben manejar correctamente los casos límite de validación, como nombres con caracteres especiales, formatos de correo electrónico inusuales, y diferentes formatos de números de teléfono internacionales.
9. Se deben validar las fechas para asegurar que la fecha de fin no sea anterior a la fecha de inicio en educación y experiencia laboral.
10. Se debe validar que el tipo de archivo del CV sea uno de los tipos permitidos.
