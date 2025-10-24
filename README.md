# 🚀 Laravel + Docker: Guía de Uso

## 1. Levantar el entorno

```bash
docker compose up -d --build
```

- Inicia los servicios de Laravel y MySQL.
- Accede a la app en [http://localhost:8000](http://localhost:8000).

## 2. Instalar dependencias (si es necesario)

```bash
docker compose exec app composer install
```

## 3. Configurar variables de entorno

- Copia `.env.example` a `.env` y ajusta tus variables.
- Genera la clave de la aplicación:

```bash
docker compose exec app php artisan key:generate
```

## 4. Migraciones y seeders

```bash
docker compose exec app php artisan migrate
docker compose exec app php artisan db:seed
```

## 5. Comandos útiles

- **Entrar al contenedor:**
  ```bash
  docker compose exec app bash
  ```

- **Ejecutar Artisan:**
  ```bash
  docker compose exec app php artisan <comando>
  ```

- **Instalar paquetes con Composer:**
  ```bash
  docker compose exec app composer require <paquete>
  ```

- **Ver logs:**
  ```bash
  docker compose logs -f app
  ```

## 6. Detener el entorno

```bash
docker compose down
```

---

**Notas:**
- No necesitas instalar PHP, Composer o MySQL localmente.
- Los cambios en el código se reflejan automáticamente en el contenedor.
- Todo el desarrollo y ejecución se realiza dentro de Docker.