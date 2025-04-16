Docker é uma plataforma de virtualização de containers que permite empacotar, distribuir e executar aplicaçoes de forma isolada e consistente.

Containers Docker compartilham o kernel do sistema operacional host, tornando-os mais leves e efecientes, essa pode ser considerada a principal diferença para outras plataformas de virtualização. VMs tradicionais não compartilham o kernel e são 100% isoladas do host físico em que foram projetadas.

Outros benefecios que pode ser citados;

Isolamento: cada container roda de forma isolada, com seus proprios processos, redes e sistemas de arquivos
Portabilidade ("build once, run everywhere), inumeros ambientes podem ter Docker instalado e um containers pode ser rodado em qualquer sistema que possua o mesmo instalado.
Eficiência: Containers sao mais leves que VMs tradicioansi e iniciam mais rapidamente.
Escalabilidade: Facilita a criação e gerenciamento de multiplas instancias da aplicação
DOCKER FILE
A imagem base a ser utilizada
Comandos a serem executados durante a construção
Arquivos a serem copiados para dentro da imagem
Portas a serem expostas
Comando padrão a ser executado quando o container iniciar
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]

Principais comandos do Docker
Aqui estão os comandos mais utilizados no dia a dia com Docker:

Gerenciamento de Imagens
docker build . - Constrói uma imagem a partir de um Dockerfile
docker pull [imagem] - Baixa uma imagem do Docker Hub
docker images - Lista todas as imagens locais
docker rmi [imagem] - Remove uma imagem específica
Gerenciamento de Containers
docker run [imagem] - Cria e inicia um novo container
docker ps - Lista containers em execução
docker ps -a - Lista todos os containers (incluindo parados)
docker start [container] - Inicia um container existente
docker stop [container] - Para um container em execução
docker rm [container] - Remove um container
Logs e Debugging
docker logs [container] - Exibe logs do container
docker exec -it [container] bash - Acessa o terminal do container
Opções comuns do docker run
-d - Executa em modo detached (background)
-p [host-port]:[container-port] - Mapeia portas
-v [host-path]:[container-path] - Monta volumes
--name [nome] - Define um nome para o container
-t - Define uma tag/nome para a imagem durante o build ou execução