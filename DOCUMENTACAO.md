# CP04 DevOps | Documento de evidencias

## Equipe

- Luan - RMXXX
- Davi - RMXXX
- Cau - RMXXX
- Rui - RMXXX
- Luigi - RMXXX

Substitua `RMXXX` pelos RMs oficiais antes da entrega final.

## Como executar localmente

```bash
docker build -t cp04-site:cp04 .
docker run --rm -p 8080:80 cp04-site:cp04
```

Acesse `http://localhost:8080`.

## Evidencias para o PDF

Inclua prints legiveis destas etapas, nesta ordem:

1. `docker build -t cp04-site:cp04 .` concluido sem erro.
2. Imagem criada com `docker images`.
3. Publicacao no Docker Hub com a tag `cp04`.
4. Container ativo com `docker ps`.
5. Site aberto pelo IP ou URL publica da EC2.
6. Pagina com a equipe, os conceitos de groups e namespaces e os criterios.

## Publicacao sugerida

```bash
docker tag cp04-site:cp04 SEU_USUARIO/cp04:cp04
docker login
docker push SEU_USUARIO/cp04:cp04
```

Na EC2, abra a porta TCP 80 no Security Group e execute:

```bash
docker pull SEU_USUARIO/cp04:cp04
docker run -d --name cp04-site --restart unless-stopped -p 80:80 SEU_USUARIO/cp04:cp04
```
