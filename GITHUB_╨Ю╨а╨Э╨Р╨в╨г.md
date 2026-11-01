# GitHub арқылы сайтты интернетке шығару

**Бұл жоба Node.js серверін қажет етеді. GitHub Pages тек статикалық файлдарға арналған, сондықтан GitHub Pages арқылы аккаунттар, /api сұраулары және мұғалім панелі жұмыс істемейді.**

## GitHub + Render

1. github.com → New repository → `zhi-detektivi` → Create repository.
2. Осы архивтің **ішіндегі** `server.js`, `package.json`, `public` бумасы, `.gitignore`, `README.md` файлдарын репозиторийдің түбіріне жүктеңіз (Add file → Upload files → Commit changes). ZIP файлын тұтас жүктемеңіз.
3. render.com → New → Web Service → GitHub репозиторийін қосыңыз.
4. Language: Node; Build Command: `npm install`; Start Command: `npm start`.
5. Environment variables: `HOST=0.0.0.0`, `TEACHER_INVITE_CODE=` (ұзын, өзіңіз ғана білетін код), `COOKIE_SECURE=true`.
6. Deploy батырмасын басыңыз. Дайын болғанда Render көрсететін HTTPS сілтемені ашыңыз.

## Маңызды: аккаунт деректерінің тұрақтылығы

**Free Web Service** жергілікті `data/db.json` файлын қайта іске қосылғанда/жаңа нұсқа жариялағанда жоғалтуы мүмкін. Бұл нұсқаны тек тест үшін қолданыңыз.

Тұрақты пайдалануға: **ақылы Render Web Service + Persistent Disk** таңдаңыз. Disk mount path `/opt/render/project/src/data` болып, `DATA_DIR=/opt/render/project/src/data` болсын. Render Disk бөлімінде backup/snapshot тәртібін тексеріңіз. Көп оқушыға арналған өндірістік қолдануға жеке дерекқор, қауіпсіздік аудиті, оқушы деректерін қорғау саясаты қажет.

Бұл пакет нақты ЖИ API емес, мұғалім дайындаған жауаптарды тексеретін жаттықтырғыш.
