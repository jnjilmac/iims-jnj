# Install

```sh
# init app(`--no-github`: without github remote repository)
bootapp -l node -u jnjilmac -n jnj-iims -d "SvelteKit Client(Picocss Components, FontAwesome) with Backend(Pocketbase)" -t sveltekit-pico-fullstack

# npm link(npm install 후에는 link 해재됨, 모듈 추가시 `npm link 기존 모듈 + X` 재실행)
npm link jnj-lib-base-ts jnj-lib-google-ts jnj-lib-db-ts jnj-lib-doc-ts
```


# Run Pocketbase/Sveltekit

## Pocketbase

### create batch file

> `pb.bat`

```sh
pocketbase.exe serve --dir="_backend/pocketbase/sqlite" --http="127.0.0.1:8090"
```

### run pocketbase server

```sh
> cd C:\JnJ-soft\Projects\external\iims-jnj
> pb.bat
```

### REF: run server manually

```sh
# run pocketbase server
> pocketbase.exe serve --dir="C:/JnJ-soft/Projects/external/iims-jnj/_backend/pocketbase/sqlite" --http="127.0.0.1:8090"
# [syntax] pocketbase.exe serve --dir="<ABSOLUTE_PATH>" --http="<IP>:<PORT>"

 ➜ REST API: http://127.0.0.1:8090/api/
 ➜ Admin UI: http://127.0.0.1:8090/_/
```

## Sveltekit

```sh
# client
> yarn dev  --open

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h to show help
```


# Check In Browser

## Pocketbase

```sh
# pocketbase admin page: [syntax] `http://<IP>:<PORT>/_/`
http://127.0.0.1:8090/_/

# admin login
moondevnode@gmail.com / A*********!
```

## Sveltekit

```sh
# sveltekit server page: [syntax] `http://<IP>:<PORT>`
http://127.0.0.1:5173/
```
