### 5.27 CU-027 - Validar Ingresso (Leitura QR Code)

ID: CU-027

Nome: Validar Ingresso (Leitura QR Code)

Ator Principal: Leitor, Administrador, Parceiro Comercial

Atores Secundários: Sistema (câmera, validação)

Pré-condições: Usuário autenticado; vinculado à atração; permissão de câmera concedida

Pós-condições: Ingresso marcado como validado no sistema; registro de data/hora e usuário que validou; tabela de histórico atualizada

Requisitos Relacionados: RF-018, RF-025

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Validar Ingressos.
2. O ator clica em Iniciar Validação.
3. O sistema solicita permissão de acesso à câmera; o ator concede.
4. O sistema exibe a visualização da câmera em tempo real.
5. O ator posiciona o QR Code do ingresso no campo de leitura.
6. O sistema processa o QR Code, valida se o ingresso é da atração atual, não está cancelado e não foi validado anteriormente.
7. O sistema marca o ingresso como Validado, registra data/hora e usuário, atualiza a tabela de histórico e exibe mensagem de sucesso.

Fluxos de Exceção:

6a. QR Code inválido ou ingresso já utilizado: Sistema exibe mensagem de erro e não altera status.

6b. Ingresso cancelado: Sistema exibe mensagem "Ingresso cancelado. Entrada bloqueada."

6c. Erro de leitura do QR Code: Sistema exibe "Erro na leitura do QR Code. Tente novamente."

3a. Permissão de câmera negada: Sistema exibe mensagem informativa.
