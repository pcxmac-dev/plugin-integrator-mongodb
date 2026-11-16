# Changelog

## 0.1.0 (2026-11-16)

The first release: MongoDB as a database plugin (plugin API 2.3, liminal-libs 1.61.0; the user, 2026-11-15: "for the
integrator i need plugins for each type of database and in each plugin can setup either new databases or connections
to existing databases using many different types of IP or IPC methods. each instance in the plugin has it's own
configuration how it's shared, ports, permissions etc").

- Its own instance `local`: the server the app runs on this machine alone, never started to be asked. Its port is the
  instance's own, changed while the server is stopped and kept where the app's own module reads it.
- Connect (a database on another server, kept only when it answers, signing in where the server wants it) and New
  database (a role of its own, readWrite on that database alone, where the server signs in; the administrator asked
  once and not kept).
- One method, `tcp`; off this machine only when asked twice, over TLS and signed in.
- A sign-in is two pairs through the login: never in the value the instances are kept in, never in what a page is
  given. Every client it makes is closed after the question.
- Its API card: MongoDB through PyMongo, every address one of mongodb.com's own pages, read on 2026-11-16.
