

## CONTROL ID.RA-3: Threats, both internal and external, are identified and documented
## CONTROL PR.AC-4: Access permissions and authorizations are managed
## CONTROL PR.DS-2: Data-in-transit is protected
## CONTROL PR.DS-2: PR.IP-1: A baseline configuration of information technology systems is created and maintained
Para realizar el hardening a la base de datos verificamos la versión del motor, ejecutando el comando
SELECT SERVERPROPERTY('productversion'), SERVERPROPERTY ('productlevel'), SERVERPROPERTY ('edition')

El motor de base de datos es SQL Azure RTM version 12.0.2008. RTM (Release To Manufacturing) indica  la versión final.
Dentro de las guías de aseguramiento de CIS, se encontró un manual específico para Microsoft Azure Foundations v1.1.0 publicado el  15 de febrero de 2019. La sección 4 está dedicada a recomendaciones de seguridad para configurar en las bases de datos.  

### Definiciones de perfil
Los siguientes perfiles de configuración están definidos por este Benchmark:  
  +	 Nivel 1    
      + sea práctico y prudente.  
      +	 proporcionar un beneficio de seguridad claro.       
      +	 no inhibir la utilidad de la tecnología más allá de los medios aceptables.  
 
### Nivel 2
Este perfil extiende el perfil "Nivel 1". Los artículos en este perfil exhiben uno o más de
Las siguientes características:
o están destinados a entornos o casos de uso donde la seguridad es primordial
o actúa como defensa en medida profunda
o puede inhibir negativamente la utilidad o el rendimiento de la tecnología.


