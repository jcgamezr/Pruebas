

## CONTROL ID.RA-3: Threats, both internal and external, are identified and documented
## CONTROL PR.AC-4: Access permissions and authorizations are managed
## CONTROL PR.DS-2: Data-in-transit is protected
## CONTROL PR.DS-2: PR.IP-1: A baseline configuration of information technology systems is created and maintained
Para realizar el hardening a la base de datos verificamos la versión del motor, ejecutando el comando *SELECT SERVERPROPERTY('productversion'), SERVERPROPERTY ('productlevel'), SERVERPROPERTY ('edition')*

El motor de base de datos es SQL Azure RTM version 12.0.2008. RTM (Release To Manufacturing) indica  la versión final.
Dentro de las guías de aseguramiento de CIS, se encontró un manual específico para Microsoft Azure Foundations v1.1.0 publicado el  15 de febrero de 2019. La sección 4 está dedicada a recomendaciones de seguridad para configurar en las bases de datos.  

### Definiciones de perfil
Los siguientes perfiles de configuración están definidos por las siguientes caracteristicas:  
  +	 Nivel 1    
      + sea práctico y prudente.  
      +	proporcionar un beneficio de seguridad claro.       
      +	no inhibir la utilidad de la tecnología más allá de los medios aceptables.  
 
  + Nivel 2
      + están destinados a entornos o casos de uso donde la seguridad es primordial
      + actúa como defensa en medida profunda
      + puede inhibir negativamente la utilidad o el rendimiento de la tecnología.  
      
|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.1 |'Auditing' is set to 'On' (Scored) |1|La plataforma Azure permite crear un servidor SQL como un servicio. La habilitación de la auditoría en el nivel del servidor garantiza que todas las bases de datos existentes y creadas recientemente en la instancia del servidor SQL sean auditadas.|

|VERIFICACIÓN|REMEDIACIÓN|
|-----------------------------------------|-----------------------------------------|
|![Image of Yaktocat](41a) |![Image of Yaktocat](41b)|

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.2 |'AuditActionGroups' in 'auditing' policy for a SQL server is set properly (Scored)|1|Para capturar todas las actividades críticas realizadas en servidores SQL y bases de datos dentro de servidores SQL, la auditoría debe estar configurada para capturar los 'AuditActionGroups' apropiados SUCCESSFUL DATABASE AUTHENTICATION GROUP,FAILED DATABASE AUTHENTICATION GROUP, BATCH COMPLETED GROUP.|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](42a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.3 |'Auditing' Retention is 'greater than 90 days' (Scored)|1|Los registros de auditoría se pueden usar para detectar anomalías y dar una idea de comportamiento sospechoso o el mal uso de la información y el acceso. La retención de auditoría de SQL Server debe configurarse para que sea mayor a 90 días.|

|VERIFICACIÓN|REMEDIACIÓN|
|------------------------------------------|---------------------------------------------|
|![Image of Yaktocat](43a) |![Image of Yaktocat](43b)|

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.4|'Advanced Data Security' on a SQL server is set to 'On' (Scored)|2|SQL Server "Advanced Data Security" proporciona una nueva capa de seguridad, que permite la deteccion y respuesta a las amenazas potenciales. Los usuarios recibirán notificaciones ante actividades sospechosas, vulnerabilidades potenciales, anomalías, patrones de acceso a bases de datos y alertas de ataques de inyección SQL. La seguridad de datos avanzada es una función de pago y esta caracteristica deberia estar habilitada en servidores SQL críticos para el negocio.|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](44a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.5 |'Threat Detection types' is set to 'All'|2|La habilitación de todos los tipos de detección de amenazas protege contra la inyección de SQL, las vulnerabilidades de la base de datos y cualquier otra actividad anómala.|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](45a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.6 |'Send alerts to' is set (Scored)|2|Proporcionar la dirección de correo electrónico para recibir alertas garantiza que cualquier detección de anomalías se informan lo antes posible, lo que aumenta la probabilidad de mitigar cualquier riesgo potencial.|

|VERIFICACIÓN|REMEDIACIÓN|
|------------------------------------------|---------------------------------------------|
|![Image of Yaktocat](46a) |![Image of Yaktocat](46b)|

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.7 |'Email service and co-administrators' is 'Enabled' (Scored)|2|Habilitar a los coadministradores para recibir alertas de seguridad del servidor SQL ayuda a informar ante cualquier riesgo potencial|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](47a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.8 |Ensure that Azure Active Directory Admin is configured|1|Use la autenticación de Active Directory de Azure para la autenticación con la base de datos SQL.|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](48a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.9 |Ensure that 'Data encryption' is set to 'On' on a SQL Database (Scored)|1|El cifrado de datos transparente de la Base de datos SQL de Azure ayuda a proteger contra la amenaza de actividad maliciosa al realizar el cifrado y descifrado en tiempo real de la base de datos, las copias de seguridad asociadas y los archivos de registro de transacciones sin necesidad de cambios en la aplicación.|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](49a) |

|**ÍTEM** | **DESCRIPCIÓN** | **NIVEL** |**DETALLE**|
|---------|---------------------------------|-----|---------------------------------|
|4.10 |Ensure SQL server's TDE protector is encrypted with BYOK (Use your own key) (Scored) |2|Sobre la base de las necesidades empresariales o la criticidad de los datos / bases de datos alojados en un servidor SQL, se recomienda que el protector de TDE esté encriptado por una clave administrada por el propietario de los datos (BYOK).|

|VERIFICACIÓN|
|-----------------------------------------------------------------------------------|
|![Image of Yaktocat](410a) |





