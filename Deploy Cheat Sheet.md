export APPS_JSON_BASE64=$(base64 -w 0 ./apps.json)

```
docker build \
--build-arg=FRAPPE_PATH=https://github.com/frappe/frappe \
--build-arg=FRAPPE_BRANCH=version-15 \
--build-arg=PYTHON_VERSION=3.11.6 \
--build-arg=NODE_VERSION=20.19.2 \
--build-arg=APPS_JSON_BASE64=$APPS_JSON_BASE64 \
--tag=semesta_library:latest \
--no-cache \
--file=images/custom/Containerfile .
```

```
sed -i 's|frappe/erpnext:v15.72.3|semesta_library:latest|g' pwd.yml
sed -i 's|semesta_library:latest|frappe/erpnext:v15.70.2|g' pwd.yml
sed -i 's|--install-app erpnext|--install-app library_core|g' pwd.yml
sed -i 's|--install-app library_core|--install-app erpnext|g' pwd.yml
```

```
docker compose -p semesta_library -f pwd.yml up -d
docker compose -p semesta_library -f pwd.yml down
```

```
docker exec -it semesta_library-backend-1 /bin/bash
bench --site frontend MariaDB
SET SQL_SAFE_UPDATES = 0;
UPDATE `tabSessions` SET sessiondata = REPLACE(sessiondata, 'null', 'None') WHERE sessiondata LIKE '%null%';
SET SQL_SAFE_UPDATES = 1;
```
