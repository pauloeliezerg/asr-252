Implementação de Proxy Reverso com NGINX no Play with Docker
📚 Conceitos Fundamentais

1. Proxy Reverso
   Um proxy reverso atua como intermediário entre clientes e servidores backend:

Recebe requisições de clientes

Encaminha para servidores apropriados

Retorna respostas aos clientes

2. Componentes do NGINX como Proxy Reverso
   Upstream Blocks
   Define grupos de servidores backend:

nginx
upstream backend_servers {
server app1:80;
server app2:80;
}
Server Blocks
Configurações de servidor virtual:

Escuta em portas específicas

Define nomes de domínio

Configura regras de roteamento

Location Blocks
Define como tratar diferentes URIs:

nginx
location / {
proxy_pass http://backend_servers;
} 3. Diretivas Principais
Diretiva Função
proxy_pass Encaminha requisições para backend
proxy_set_header Modifica headers da requisição
proxy_buffering Controla buffer de respostas
proxy_cache Configura cache de conteúdo 4. Benefícios
Balanceamento de carga: Distribui tráfego entre múltiplos servidores

SSL Termination: Gerencia certificados SSL centralmente

Cache: Melhora performance com cache de conteúdo

Segurança: Oculta infraestrutura backend

Compressão: Reduz tamanho das respostas
