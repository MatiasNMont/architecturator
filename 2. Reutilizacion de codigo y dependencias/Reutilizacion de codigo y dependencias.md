# Criterios de reutilizacion de codigo. 

Se utilizan como referencias, dos de la tecnicas de reutilizacion tales como las librerias compartidas y los servicos compartidos. Tenga en cuenta que la implicacion depende de cada escenario y contexto. 

| **Criterio**               | **Custom Shared Library** | **Shared Service** |
|----------------------------|--------------------------|--------------------|
| **Definición**             | Una librería de código reutilizable que se compila e integra en múltiples aplicaciones. | Un servicio independiente que ofrece funcionalidades accesibles a través de APIs. |
| **Código heterogéneo**     | ❌ No soporta múltiples lenguajes fácilmente, ya que depende del lenguaje de la aplicación que la usa. | ✅ Compatible con múltiples lenguajes, ya que se accede por API. |
| **Alta volatilidad de código** | 🚨 Impacta directamente a todas las aplicaciones que la usan, requiriendo recompilación y redeploy. | ✅ Puede actualizarse de forma independiente sin afectar a los clientes inmediatamente. |
| **Capacidad de cambios de versiones** | ⚠️ Difícil de versionar. Se necesita compatibilidad retroactiva o mantener múltiples versiones en cada aplicación. | ✅ Fácil de versionar mediante endpoints (ej. `/v1/login`, `/v2/login`). |
| **Overall Change Risk**    | 🔴 Alto. Cambios pueden romper todas las aplicaciones que dependen de la librería. | 🟢 Bajo. Se puede actualizar sin afectar clientes si hay versionado correcto. |
| **Performance**            | 🟢 Alto rendimiento porque se ejecuta en memoria dentro del proceso de la aplicación. | ⚠️ Menor rendimiento por latencia de red y sobrecarga de procesamiento HTTP/RPC. |
| **Tolerancia a fallos**    | ❌ Si la librería tiene un bug, todas las apps deben actualizarse. No hay fallback automático. | ✅ Puede desplegarse con alta disponibilidad y manejar errores sin afectar a todas las aplicaciones. |
| **Escalabilidad**          | ❌ Depende de cada aplicación. No escala de manera independiente. | ✅ Se puede escalar horizontalmente con balanceadores de carga y múltiples instancias. |

