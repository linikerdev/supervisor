#Arquivo de configuração do supervisor

** colocar na pasta 

```
etc\supervisor\conf.d\nomedoarquivo
```
**Segue alguns comandos

```
sudo supervisorctl update
sudo supervisorctl stop projeto:*
sudo supervisorctl start projeto:*
sudo supervisorctl status projeto:*
```

```
[program:filas]
process_name=%(program_name)s_%(process_num)02d
command=php /home/forge/app.com/artisan queue:work sqs --sleep=3 --tries=3
autostart=true
autorestart=true
user=forge
numprocs=8
redirect_stderr=true
stdout_logfile=/home/forge/app.com/worker.log
```