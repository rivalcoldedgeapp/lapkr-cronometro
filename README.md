# LapKr · Cronómetro

App de cronometraje en vivo para LapKr Team. Hasta 4 carriles en paralelo, estado compartido en tiempo real entre el equipo vía Firestore.

## Stack

- HTML/CSS/JS puro (sin bundler)
- Firebase Auth (Google) — mismo proyecto que el dashboard
- Firestore — sesión activa compartida + histórico por evento

## Estructura Firestore

```
config/lapkr-team               (auth — ya existe, compartido con dashboard)
cronometro/activa               (sesión actual del equipo, 1 doc)
cronometro-historico/{id}       (sesiones archivadas)
```

## Deploy

1. Conectar repo a Vercel.
2. Sin build step — Vercel sirve `index.html` directo.
3. URL: `lapkr-cronometro.vercel.app`

## Acceso

Solo miembros del equipo LapKr con la tarjeta `cronometro` asignada en el dashboard pueden usar la app. La autorización se gestiona desde el modal de equipo del dashboard.

## Uso

- Hasta 4 carriles en paralelo (nombre editable por carril).
- Botón TAP grande para marcar vuelta — pensado para usar con guante.
- Última vuelta + mejor vuelta resaltada en azul.
- Sesión asociada a un evento (Telmex, SKUSA, entrenamiento, etc.).
- Al archivar, la sesión se guarda en histórico filtrable por evento.

## Convenciones

- Hungarian: `strFoo`, `lstBar`, `objBaz`, `intN`, `boolX`.
- Sin gradientes/sombras pesadas. Mismo estilo visual que el dashboard.
