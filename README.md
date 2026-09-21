[LEEME.md](https://github.com/user-attachments/files/32469269/LEEME.md)
# Historias clínicas — versión de un solo archivo

Abre `historias-clinicas.html` con doble clic. No hay nada que instalar.

**Entrar:** `terapeuta@demo.local` · `demo1234` (también `admin@demo.local` con la misma
contraseña, que ve las fichas de todos).

Vienen tres pacientes ficticios con sesiones, tratamientos y tareas para que puedas probarlo
todo sin escribir nada. Cuando quieras empezar en serio: Configuración → Borrar todos los datos.

---

## Lo que funciona completo

Fichas de paciente con archivado en lugar de borrado, consentimiento informado con firma
escrita, consultas con notas editables siempre y autoguardado a los dos segundos, historial de
cambios campo a campo, tratamientos, tareas, línea de tiempo con gráfico de ánimo, y los cinco
reportes en PDF con encabezado del consultorio, numeración de páginas y tu firma al pie.

## Lo que un navegador no puede hacer solo

**El email no sale automáticamente.** Una página web no puede hablar SMTP. Al pulsar enviar se
descarga el PDF y se abre tu programa de correo con destinatario, asunto y mensaje ya escritos:
adjuntas el archivo y le das a enviar.

**WhatsApp tampoco adjunta archivos desde un enlace.** Mismo procedimiento: PDF descargado y la
conversación abierta con el texto redactado, listo para adjuntar desde el clip.

Por eso los envíos quedan registrados como *Preparado*, y tú los marcas como enviados cuando lo
confirmes. Si en algún momento quieres envío automático de verdad, hace falta un servidor.

## Dónde se guardan los datos

En IndexedDB, dentro de este navegador y este equipo. Si abres el archivo con Chrome haciendo
doble clic, Chrome bloquea IndexedDB en archivos locales y la app pasa sola al almacenamiento
simple del navegador (te avisa arriba). Dos formas de tener IndexedDB de verdad:

- Abrir el archivo con **Firefox**, que sí lo permite en local.
- O servirlo: `npx serve` en la carpeta, y entrar por `http://localhost:3000`.

**No hay copia de seguridad automática.** Si borras los datos de navegación, cambias de
ordenador o usas el modo incógnito, se pierde todo. En Configuración tienes *Descargar copia de
seguridad*: un JSON con todo, que puedes restaurar desde el mismo sitio. Hazlo con regularidad.

La primera vez necesita conexión para descargar la librería que genera los PDF. Después
funciona sin internet, salvo esa parte si vacías la caché.

## Privacidad

Esto maneja datos de salud, que son datos de categoría especial. Que no haya servidor reduce la
exposición pero no la elimina: quien tenga acceso al equipo tiene acceso al navegador, y la
sesión se cierra al recargar precisamente por eso. **No es un sistema conforme a RGPD ni a
HIPAA por sí mismo.** Cifra el disco, bloquea la sesión del sistema operativo y guarda las
copias de seguridad en un sitio protegido. Consúltalo con un especialista antes de usarlo con
pacientes reales.
