## path
* cumprimentar
  - action_cumprimentar
  - action_definir_perfil
> identifica_perfil




<!--- Fluxo Curiosidades --->

## path1
> identifica_perfil
* afirmar_curiosidades
  - action_curiosidades_indicacao
> identificar_curiosidade

## path1.end.1
> curiosidade_final
* afirmar
  - action_curiosidades_mais_sim
> identificar_curiosidade

## path1.end.2
> curiosidade_final
* negar
  - action_curiosidades_mais_nao
> curiosidade_falar_sobre_projetos

## path1.end.2.1
> curiosidade_falar_sobre_projetos
* afirmar
  - action_curiosidades_falar_sobre_projetos
  - action_aviso
> identificar_preenchimento_de_proposta

## path1.end.2.2-fim
> curiosidade_falar_sobre_projetos
* negar
  - action_despedir




<!--- Fluxos Propostas e Projetos --->

## path2
> identifica_perfil
* afirmar_projeto
  - action_aviso
> identificar_preenchimento_de_proposta

## path2.1
> identificar_preenchimento_de_proposta
* afirmar_preencheu_proposta
  - action_nova_proposta
> identificar_nova_proposta

## path2.2
> identificar_preenchimento_de_proposta
* negar
  - action_conhece_processo
> identificar_conhecimento_de_processo

## path2.3
> identificar_preenchimento_de_proposta
* o_que_eh
  - action_o_que_eh
> identificar_conhecimento_de_processo

## path2.1.1
> identificar_nova_proposta
* afirmar_nova_proposta
  - action_introduzir_contexto_nova_proposta
> identificar_contexto

## path2.1.2
> identificar_nova_proposta
* negar
  - action_duvida_execucao
> identificar_execucao




<!--- Fluxo de Execução --->

## path2.1.2.1-fim
> identificar_execucao
* afirmar_execucao
  - action_introduzir_execucao
  - action_despedir

## path2.1.2.2
> identificar_execucao
* negar
  - action_introduzir_contexto_nao_execucao
> identificar_contexto

## path2.1.2.3
> identificar_execucao
* o_que_eh
  - action_o_que_eh
  - action_duvida_execucao
> identificar_execucao



<!--- Conhecimento do Processo --->

## path2.2.1
> identificar_conhecimento_de_processo
* afirmar
  - action_cadastro_salic
> identificar_cadastro_salic

## path2.2.2
> identificar_conhecimento_de_processo
* negar
  - action_submissao_de_projetos
  - action_cadastro_salic
> identificar_cadastro_salic

## pathCadastroSalic.1
> identificar_cadastro_salic
* afirmar
  - action_ja_eh_proponente
> identificar_eh_proponente

## pathCadastroSalic.2
> identificar_cadastro_salic
* negar
  - action_cadastro_salic_video
> identificar_explicar_cadastro

## pathCadastroSalic.3
> identificar_cadastro_salic
* o_que_eh
  - action_o_que_eh
> identificar_explicar_cadastro

## pathCadastroSalic.2.1
> identificar_explicar_cadastro
* afirmar
  - action_explicar_cadastro_salic
  - action_inscricao_proponente
  - action_cadastro_proponente_introduzir_contexto
> identificar_contexto


## pathCadastroSalic.2.2
> identificar_explicar_cadastro
* negar
  - action_cadastro_salic_apos_video
  - action_inscricao_proponente
  - action_cadastro_proponente_introduzir_contexto
> identificar_contexto

## pathCadastroProponente.1
> identificar_eh_proponente
* afirmar
  - action_cadastro_proponente_introduzir_contexto
> identificar_contexto

## pathCadastroProponente.2
> identificar_eh_proponente
* negar
  - action_inscricao_proponente
  - action_cadastro_proponente_introduzir_contexto
> identificar_contexto

## pathCadastroProponente.3
> identificar_eh_proponente
* o_que_eh
  - action_o_que_eh
  - action_cadastro_proponente_introduzir_contexto
> identificar_contexto

## pathContexto.1
> identificar_contexto
  - action_definir_contexto
* escolher_processo
> opcao_processo

## pathContexto.2
> identificar_contexto
  - action_definir_contexto
* escolher_preenchimento
> opcao_preenchimento

## pathContexto.3
> identificar_contexto
  - action_definir_contexto
* escolher_prazo
> opcao_prazo

## pathContexto.4
> identificar_contexto
  - action_definir_contexto
* escolher_correcao
> opcao_correcao

## pathContexto.5
> identificar_contexto
  - action_definir_contexto
* escolher_erros_salic
> opcao_erros_salic

## pathContexto.x
> identificar_contexto
  - action_definir_contexto
* o_que_eh
  - action_o_que_eh
  - action_mais_alguma_pergunta
> identifica_mais_alguma_pergunta

## pathMaisPergunta.1
> identifica_mais_alguma_pergunta
* afirmar
  - action_mais_perguntas_afirmativa
> identificar_contexto

## pathMaisPergunta.2-fim
> identifica_mais_alguma_pergunta
* negar
  - action_despedir