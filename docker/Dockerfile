# Use a imagem oficial do pgvector
FROM pgvector/pgvector:pg17

# Variáveis de ambiente
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=qualquer_uma
ENV POSTGRES_DB=BD_PESQUISADOR
ENV POSTGRES_HOST_AUTH_METHOD=trust

# Copia script de inicialização
COPY init_db.sh /docker-entrypoint-initdb.d/init_db.sh

# Dá permissão
RUN chmod +x /docker-entrypoint-initdb.d/init_db.sh

# Porta do banco
EXPOSE 5432