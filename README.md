# tp-final

# Ecosistema de Automatización IA Autónomo para Negocios - Trabajo Final
**Estudiante:** Federico  
**Curso:** Automatización de IA en Coderhouse  
**Stack Tecnológico:** Make (Orquestador), Airtable (Base de Datos), OpenAI o4-mini (Procesamiento), Slack & Gmail (Canales de Salida).

## 🔗 Enlaces Obligatorios del Proyecto
* 📊 **Link en Modo Lectura a la Base de Datos (Airtable):** https://airtable.com/appKAebIoG8oTJORo/shr5UPWzweOpbfE4M
* 🤖 **Lógica del Flujo (Archivo Técnico):** [[link](https://www.youtube.com/watch?v=lkPeWLFX3x8)](./logicadeflujo.blueprint)
* 📄 **Documentación Completa y Evidencias:** [link](./documentacion_evidencia.pdf)

---

## 🛠️ Descripción del Proceso de Negocio
El sistema resuelve de extremo a extremo el proceso de **Triage Inteligente, Calificación de Leads VIP y Automatización de Propuestas Comerciales** sin intervención manual en su procesamiento inicial.

1. **Ingestión (Trigger):** Se activa de forma eficiente mediante un campo inteligente *Last Modified Time* en Airtable que observa cambios únicamente en la columna `Estado` cuando pasa a `Pendiente`.
2. **Cerebro (IA):** OpenAI procesa el mensaje utilizando el modelo `o4-mini` bajo un formato estructurado obligatorio (`JSON Object`), evaluando semánticamente si el cliente requiere atención prioritaria.
3. **Enrutamiento:** Un Router bifurca el pipeline. Los leads regulares se archivan de manera automática como `Aprobado` asignándoles la categoría `Regular`. Los leads de alto valor (`VIP`) entran en la ruta de gobernanza corporativa.
4. **Human-in-the-loop (HITL):** El sistema congela el flujo VIP actualizando Airtable al estado `HITL_Validacion` y envía una notificación estructurada al canal corporativo de Slack para su auditoría manual.
5. **Salida Multicanal:** Al cambiar físicamente el estado a `Aprobado` en el Dashboard de Airtable, el Router del inicio reactiva el flujo enviando la propuesta comercial final validada mediante la API de Gmail.
