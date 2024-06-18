# AppPainel

Dashboard{
    Filtro pesquisa avançada: gráfico mês
    Licença de operador
    Licença de conversas
    Licença de WhatsApp
    Licença telegrama
    Licença chat
    Licença Acesso remoto

    Cadastros {
        Grupos {
            Pesquisa Avançada – SMTP sim/não
            Ao lado de pesquisa avançada tem um input de pesquisa e uma setinha, que filtra por grupos ativos ou não ativos
            Nesse botão setinha tem a opção de exportar grupos, contém; Sequencia, nome, email, distribuir chamados aos operadores (online ou offline), distribuir chamados aos operadores (somente online), distribuir chamados aos operadores nas transferências do chamado, distribuir chamados aos operadores por cliente e/ou especialidade, deixar na fila caso não haja cliente ou especialidade relacionada, quantidade de chamados distribuídos para os operadores, distribuir chamados aleatoriamente, desabilitar o envio das respostas automáticas de chamados para este grupo
            Também tem a opção de importar
            Nome – Email – Opções (Distribuição automáticas de trabalho) – SMTP

            Mouse direito no grupo – Desativar, excluir
            Não é possível desativar grupos com auto categorias vinculadas aquele grupo

            Criar Grupos {
                Nome
                Email
                Distribuir chamados para operadores automaticamente – Esta função faz a distribuição dos Chamados para os Operadores. Independentemente eles estando online ou não.
                Distribuir Chamados para os Operadores (Online) Automaticamente - Esta função faz a distribuição dos Chamados para os Operadores que estejam online.
                Distribuir Chamados para os Operadores nas Transferências - Esta função faz a distribuição dos Chamados quando um Operador usa algum status de Transferência. É dependente de um dos dois recursos acima.
                Distribuir Chamados aos Operadores por Cliente e/ou Especialidade -Esta função faz a distribuição dos Chamados quando um Operador tem preferência no atendimento de uma Empresa (Cliente) e/ou Especialidades (Categoria e Sub-Categoria). PS: (Se não tiver ninguém com especialidade, fica na fila)
                Deixar na Fila Caso não Haja Cliente ou Especialidade Relacionada - Não Distribuir o Chamado quando não houver Cliente e/ou Especialidade para os Operadores.
                Quantidade de Chamados Distribuídos para os Operadores - Em caso de redistribuição de atendimentos via Chat/WhatsApp/Telegram (Configurações de Conversas), olha a quantidade atual de atendimentos do Operador para sorteá-lo no recebimento do que estava na fila.
                Distribuir Chamados para os Operadores Aleatoriamente Sim: Faz a Distribuição dos Chamados para os Operadores de forma totalmente aleatória. Não: Faz a Distribuição dos Chamados para os Operadores com os menos chamados ou aleatoriamente caso a quantidade entre eles seja igual. (Não analisa o balanço de carga, mas balança a especialidade)

                Operadores (Pertence ao grupo – nome – status – recebe – total de chamados; associado ao grupo – nome – status – recebe – total de chamados)
                Diferenças entre pertence a associado; pertence = grupo principal, associado = grupo adicional

                Avançado (Desabilitar o Envio das Respostas Automáticas de Chamados para este Grupo - Ao ativar esta permissão, você impedirá o envio de respostas automáticas de chamados para qualquer solicitante que enviar um e-mail para este grupo. Isso significa que os membros do grupo não receberão mensagens automáticas de confirmação ou atualização em relação aos chamados.)
            }
        }

        Aba SMTP {
            Observação (Ao Cadastrar o SMTP do Grupo de Atendimento, todos os chamados respondidos por Operadores deste grupo serão disparados pelo Email abaixo.
            Além dos Chamados também serão disparadas as Pesquisas de Satisfação Vinculadas a estes grupos de atendimento. Caso não tenha nada configurado, será usado o Padrão do Desk Manager ou o Email geral do Ambiente.)
            SMTP{
                Nome
                Tipo – Padrão ou Amazon SES e SendGrid
                Email – desejo usar o meu servidor do SMTP
                Senha do email – Porta
                SMTP
            }
        }

        Associar Licenças ao grupo {
            Operador; consegue subdividir as licenças no grupo certo. Exemplo (de 10 licenças 2 vão ser usadas no grupo de infra, quero ter a certeza que essas 2 licenças só vão ser utilizadas no operador do grupo de infra, então ele trava as licenças)
            Fornecedor;
            RCS;
            Conversas;
            Chat;
            WhatsApp;
            Telegram;
            Teams;
        }
    }
}

Operadores {
    Geral {
        Nome – Sobrenome
        Email
        Telefone – Celular
        Ramal – SMS
    }
    
    Licença {
        Operador
        Fornecedor
        RCS
        Conversas
        Chat
        Whatsapp
        Telegram
        Teams
        Mapa de Atendimento
    }

    Acesso ao Sistema {
        Login
        Senha – Confirmar senha
        Autenticação
        Forçar a Mudança de Senha – primeiro acesso vai ser forçado a trocar a senha
        Envio de Boas-Vindas
        Administrador – hierarquia é adm, gerente, operador comum (Adm criar operador em qualquer time - gerente somente no seu grupo principal)
        Gerente do Sistema – pode mudar somente ao seu próprio grupo
        Liberação de Acesso por IP
        Liberação de Acesso por IP do Cliente
        Logar com Google Account
        Logar com Microsoft Account
        Habilitar Acesso ao Sistema – quando o operador entrar de férias, licença maternidade
    }

    Grupo de Atendimento {
        Guia Principal
        Grupos Adicionais
        Ao Atualizar o Perfil Atualizar também este Operador
        Habilitar visualização de todos os Chamados de seus Grupos de Atendimento
        Habilitar visualização de Chamados apenas do próprio Operador e da Fila
        Enviar todas as Notificações de Chamados para o Email do Grupo de Atendimento
        Receber chamados distribuídos pelo grupo principal?
    }

    Perfil {
        Associado ao Perfil
        Ao atualizar o perfil, atualizar também este operador
    }

    Dados Pessoais {
        Perfil Profissional {
            Admissão – visível
            Valor hora – hora/mês – fazer hora extra
            Chamados por mês
            Cargo – ao editar o perfil atualize o operador
            Função – ao editar o perfil atualize o operador
        }
        
        Superior {
            Operadores – ao editar o perfil atualize o operador
        }
        
        Competencia {
            Competencias
        }
        
        Especialidade {
            Categorias – Para a distribuição de chamados, aqui que identifica quais as especialidades
        }
        
        Atendimento ao cliente {
            Clientes – Preferencia do cliente ao operador
        }
        
        Atendimento a grupo de empresas {
            Grupo de empresas – Preferencia do grupo de clientes ao operador
        }

        PS:Esses 3 detalhes se somam, se a categorias, o cliente e o grupo de empresas bater 3 todos requisitos, esse operador que vai ser chamado

        Dados Pessoais {
            Data nasc
            Sexo
            Fumante
            Estado civil
            Habilitação
            Telefone 1 telefone 2
            Celular 1 celular 2
            Skype
            Email 1 email 2 email 3
            Cep
            Endereço
            Numero

            Redes sociais {
                Facebook
                Twitter
                Linkedin
                MySpace
                Tumblr
            }
        }
    }
}

Regras de Restrição {
    Permissão a transferir para grupos {
        Se deixar os campos em brancos, siginifica que nao tem nenhuma regra imposta
        Permitir – o operador só vai ter permissão para transferir somente para outros setores
        Restringir -  o operador não vai ter a permissão para transferir para esses setores
    }

    Limitar chamados e informações de clientes{
        Se uma empresa tem varias filiais, determinado operador irá ver somente determinadas filiais, na lista e informações
        Permitir
        Restringir
    }

    Limitar chamados e informações de grupos de empresas {
        Se uma empresa tem vários grupos de empresa, determinado operador vai ver somente determinados grupos de empresas
        Permitir
        Restringir
    }

    Liberação de Acesso pelo IP da Empresa{
        Bloqueando os ips que o operador não pode se conectar
        Bloqueio
    }
}

Horários de acesso {
    Dentro desses horários os operadores vão ficar bloqueados
    Hora/dia seg ter qua qui sex sab dom
}

Assinatura {
    Linha de assinatura exclusiva para o operador
    Pode colocar a assinatura do google 
}

Campos padrões para abertura de chamados{
    Especificar a categorização do chamado de um operador, exemplo, se esse operador so trabalha com trabalhos de alto risco, todos os impactos serão alta e urgência alta
    Solicitação
    Tipo de ocorrência
    Impacto – urgência
    Categoria
    Tipo

    Campo padrão para interação de chamados {
        Atribuir padrão para forma de atendimento e causa
    }
}

API{
    Chave de API do operador
    Chave de API do ambiente
}

Log de Acesso e Log {
    Log de Acesso – Toda vez que o operador acessou ou tentou acessar a plataforma
    Log – Log de cada ação que alguém fez dentro das informações daquele operador
}

Exportar-XSL
Importar-XSL (Recomendado planilha modelo)
}

Gerente Operador {
    Gerente principal de um grupo, exemplo o gerente de suporte N2, fica limitado aos operadores do seu grupo

    Mouse direito no gerente operador – desativar, excluir, atualizar
    Exportar-XSL
    Importar-XSL (Recomendado planilha modelo)

    Criar Gerente Operador {
        Geral {
            Nome – Sobrenome
            Email
            Telefone Celular
            Ramal SMS
        }
        
        Licença{
            Operador
            Fornecedor
            RCS
            Conversas
            Chat
            Whatsapp
            Telegram
            Teams
        }	
        
        Acesso ao Sistema {
            Login
            Senha – Confirmar senha
            Forçar mudança de senhas
            Enviar boas vindas
        }

        Perfil {
            Associado ao perfil – Se eu não tenho acesso a tal app, meus operadores também não vao ter
        }
    }

    Dados pessoais {
        Perfil profissional – admissão
        Competencia
        Especialidade – Categorias
        Atendimento ao Cliente
        Atendimento a Grupos de empresas
        
        Dados pessoais {
            Data Nasc
            Sexo
            Fumante
            Estado civil
            Habilitação
            Telefone 1 2 3 
            Celular 1 2 
            Skype
            Email 1 2 3
            Cep
            Endereço
            Numero

            Rede social {
                Facebook
                Twitter
                Linkedin
                MySpace
                Tumblr
            }
        }
    }
}

Perfil de Operador {
    Padronizar os acessos as permissões, através de grupos hierárquicos de operadores
    Clicar em + - consegue ver qual o nome dos operadores pertence aqueles grupos de operadores
    Exportar - XSL
    Importar – XSL (Recomendável que tenha a planilha modelo)

    Criar Perfil de Operador {
        Aqui você configura no macro, por grupo, os operadores vão herdar, estará personalizando tudo
        Horas por Mês
        Chamados por Mês
        Cargo - Ao Editar o Perfil Atualize o Operador (Automaticamente amarra para o operador, passa dinamicamente para o operador)
        Função - Ao Editar o Perfil Atualize o Operador (Automaticamente amarra para o operador, passa dinamicamente para o operador)

        Superior – Operadores
        Especialidade – Categorias
        Atendimento a Grupos de Empresas – Grupo e Empresas
    }
}

Regra de Restrição {
    Limitar a visualização de operadores por perfis de operadores (Permitir e Restringir)
    Permissão a Transferir para Grupos (Permitir e Restringir)
    Limitar Chamados e informações de Clientes (Permitir e Restringir) 
    Limitar Chamados e informações de Grupos de Empresas (Permitir e Restringir)
    Liberação de Acesso pelo IP da Empresa (Permitir e Restringir)
}

Horários de acesso {
    Dentro desses horários os operadores vão ficar bloqueados
    Hora/dia seg ter qua qui sex sab dom
}

Assinatura {
    Linha de assinatura exclusiva para o operador
    Pode colocar a assinatura do google 
}

Operadores{
    Qual operador vai ser associado a esse grupo de operadores
    Nome:
}

Campos Padrões para Abertura de Chamados {
    Ocultar algo tipo de padrão para abertura de chamados, sendo – Solicitação, Tipo de Ocorrencia, Impacto – Urgencia, Categoria, Tipo
}

Campo padrão para interação de chamados {
    Já padroniza a forma de atendimento e causa
}

Log {
    Últimas alterações feitas no registro
}

Slide Show {
    Configurar o play do slide show
    Criar slide show {
        Nome 
        Permissões – Grupo Principal, Operadores
    }
    Adicionar configurações {
        Tipo
        Ordem
        Top
        Duração – em segundos
    }
    Pode ativar e desativar os slide show

    Menu – Funções, Cargos, Competências, Estado Civil e Habilitação {
        Dados informativos que não interferem diretamente ao sistema
        Todos esses menus têm
        Botão de atualizar
        Listagem de registros
        Botão de pesquisar
        Botão de filtrar em ativos, não ativos
        Exportar e importar – XSL (excel)
        PS: Importante ter a planilha de modelo - recomendável

        Modal de criação de algum de menus {
            Nome
            Botão de continuar criando
            Salvar
        }

        Ao clicar do lado direito de um nome: Desativar, atualizar, excluir
        Log de registros
    }
}

Configurações {
    Sistema {
        Geral {
            Título do Sistema
            Título do Portal – necessário que seja 143x46 pixels em formato de .gif 
        }
        Avançado {
            Solicitante - Permite que o Solicitante possa interagir em qualquer chamado por e-mail, desde que ele tenha colocado o número do chamado no Assunto, independente do chamado estar aberto em nome da empresa principal dele ou não.
            Operadores - Envia alerta para os emails acima se o Operador finalizar mais do que X Chamados que no Mês corrente
        }
        Portal do operador {
            Limitar a visualização das listas pelo Idioma do Operador
            Dica: Essa permissão, quando desativada, sempre mostrará as listas em Português.
            Agora, quando ela estiver ativa e as listas têm traduções cadastradas, elas serão exibidas no idioma do Operador.
        }
        Horas de Inatividade {
            Desloga da Interface os Operadores/Solicitantes que estiverem acima da hora mencionada!
            *Considera o tempo de uma aba do navegador fechada!
        }
    }

    Política de senhas {
        Operadores {
            Quantidade mínima de Caracteres
            Exigir pelo menos 1 letra(s) maiúscula(s). 
            Exigir pelo menos 1 número(s).
            Exigir pelo menos 1 caractere(s) especial(is).
            Bloquear Repetição de Senhas. 
            Forçar Mudança de Senhas – por dias
        }
        Solicitantes {
            Quantidade mínima de Caracteres
            Exigir pelo menos 1 letra(s) maiúscula(s).
            Exigir pelo menos 1 número(s).
            Exigir pelo menos 1 caractere(s) especial(is).
            Bloquear Repetição de Senhas – impede do operador de repetir as 12 últimas senhas
            Forçar Mudança de Senhas – por dias
        }
    } 

    Bloquear extensão de arquivos {
        Extensão;
    }
}

Campos extras {
    Detalhes importantes que permite colocar informações adicionais em formulários específicos, para que deixe mais assertivo o resultado

    Criar Campos Extras {
        Nome – Obrigatório Sim/Não
        Label (Opcional)
        Label de Explicação (Opcional) - solicitante
        Máscara (Opcional) - Exemplos (
            Tipo    Descrição
            [calendar]    Ícone de Calendário
            [number]    Somente Número
            [number][0-10]    Somente Número de 0 a 10
            [text]    Somente Texto
            [text][3-5]    Somente Texto entre 3 a 5 caracteres
            [textarea]    Textarea
            0000-0000    Telefone
            (00) 0000-0000    Telefone
            000.000.000.000    IP
            00/00/0000    Data
            00:00:00    Hora
            ##0,00%    Percentual
            #.##0,00    R$
        )
        Lista – Multiplica Sim/Não
        Tipo 
        Exibir no grid de chamados na ordem
        Permissão a grupo – Container (Ao marcar campo extra como container ele não poderá ser utilizado como condição)
        Avançado  - Não Exibir este Campo Extra na Pesquisa Avançada de Chamados/GMUDs (Para melhor performance no grid de Chamados/GMUDs marque este opção!)
    }

    Icon de casinha – Mostrar o campo extra para o solicitante
    Mouse direito no campo extra – Atualizar, Excluir
    Importar e Exportar – XSL (Excel)
}
