### 3.20 Detalhes da Atrações/Editar da Atração - Administrador

**ID:** RF-020

**Módulo:** Detalhes da Atração &gt; Editar Atração

**Perfis com Acesso:** Administrador, Editor, Parceiro Comercial (Editor e Parceiro apenas nas atrações vinculadas)

**Prioridade:** Média (Importante)

**Descrição:** o sistema deverá exibir wizard de 3 etapas da rotina de criação de atrações RF-013, permitindo o Administrador/Parceiro Comercial editar informações da atração.

Requisitos Detalhados

| ID        | Requisito                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-020.01 | O sistema deve exibir o mesmo wizard de 3 etapas do RF-013 em modo edição, ao acessar o submenu "Editar Atração" a partir de Detalhes da Atração (RF-004).                                                                                                                                                                                                                                                                                                                                     |
| RF-020.02 | Os campos editáveis restringem-se às Etapas 1 e 2: Etapa 1 – Foto de Capa, Dados do Evento (Local, CEP, Estado, Cidade, Endereço, Número, Complemento), Sessões do Evento; Etapa 2 – Materiais (Home, Imagem da atração, Fundo), Link de vídeo, Release.                                                                                                                                                                                                                                       |
| RF-020.03 | A Etapa 3 (Dados do Ingresso) não se aplica à rotina Editar Atração.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| RF-020.04 | O sistema deve exibir botões para adicionar, remover e alterar fotos (alterar = substituir o arquivo naquela posição, mantendo as demais).                                                                                                                                                                                                                                                                                                                                                     |
| RF-020.05 | Foto de Capa e materiais (Home, Imagem da atração, Fundo): tamanho máximo 5 MB cada; formatos PNG, JPEG.                                                                                                                                                                                                                                                                                                                                                                                       |
| RF-020.06 | O sistema deve exibir mensagem informativa de que a resolução ideal para foto de capa é 500×500 px (sem bloqueio de upload). RF-020.07 O sistema deve validar que o link de vídeo promocional seja exclusivamente do YouTube (youtube.com ou youtu.be); rejeitar URLs de outros domínios. RF-020.08 O sistema deve permitir apenas um link de vídeo YouTube por atração. RF-020.09 Editor e Parceiro Comercial devem acessar "Editar Atração" somente para atrações às quais estão vinculados. |
| RF-020.07 | O sistema deve validar que o link de vídeo promocional seja exclusivamente do YouTube (youtube.com ou youtu.be); rejeitar URLs de outros domínios.                                                                                                                                                                                                                                                                                                                                             |
| RF-020.08 | O sistema deve permitir apenas um link de vídeo YouTube por atração.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| RF-020.09 | Editor e Parceiro Comercial devem acessar "Editar Atração" somente para atrações às quais estão vinculados.                                                                                                                                                                                                                                                                                                                                                                                    |

Regras de Negócio

| ID        | Regra                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------|
| RN-020.01 | Resolução ideal da foto de capa é 500×500 px; exibir mensagem informativa ao usuário, sem bloquear upload.            |
| RN-020.02 | Limite de 5 MB por foto (capa e materiais). Formatos aceitos: PNG, JPEG.                                              |
| RN-020.03 | Botões adicionar, remover e alterar para cada foto; alterar = substituir arquivo naquela posição, mantendo as demais. |
| RN-020.04 | Link de vídeo promocional deve ser obrigatoriamente do YouTube (youtube.com ou youtu.be).                             |
| RN-020.05 | Apenas um link de vídeo YouTube por atração.                                                                          |
| RN-020.06 | Editor e Parceiro Comercial acessam "Editar Atração" somente para atrações às quais estão vinculados.                 |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                             |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-020.01 | Dado que o usuário acessa Detalhes da Atração > Editar Atração, quando a tela abre, então o sistema exibe os mesmos campos do RF-013 (fotos, release, sessões, endereço, link YouTube) em modo edição, Etapas 1 e 2. |
| CA-020.02 | Dado que o usuário envia foto de capa ou material com tamanho > 5 MB, quando confirma, então o sistema exibe mensagem de erro e não aceita o arquivo.                                                                |
| CA-020.03 | Dado que o usuário informa link de vídeo que não seja do YouTube, quando salva, então o sistema exibe mensagem de erro e não salva.                                                                                  |
| CA-020.04 | Dado que o usuário clica em "Alterar" em uma foto e escolhe novo arquivo, quando confirma, então o sistema substitui a foto naquela posição, mantendo as demais.                                                     |
| CA-020.05 | Dado que Editor ou Parceiro Comercial acessa Editar Atração de atração não vinculada, quando tenta acessar, então o sistema impede o acesso ou não exibe a opção.                                                    |
| CA-020.06 | Dado que o sistema exibe mensagem sobre resolução 500×500 para foto de capa, quando o usuário envia foto com outras dimensões, então a mensagem é apenas informativa e o upload não é bloqueado.                     |

### 3.21 Detalhes da Atrações/Usuários - Administrador
