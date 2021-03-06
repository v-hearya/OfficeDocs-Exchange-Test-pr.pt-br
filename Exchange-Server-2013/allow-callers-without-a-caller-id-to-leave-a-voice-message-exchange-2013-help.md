﻿---
title: 'Permitir que os chamadores sem ID de chamadas deixem uma mensagem de voz'
TOCTitle: Permitir que chamadores sem ID de chamador deixar uma mensagem de voz
ms:assetid: 51367d98-e17c-4bcf-8b14-208bd1ac3af0
ms:mtpsurl: https://technet.microsoft.com/pt-br/library/Bb232040(v=EXCHG.150)
ms:contentKeyID: 50485577
ms.date: 05/22/2018
mtps_version: v=EXCHG.150
ms.translationtype: MT
---

# Permitir que chamadores sem ID de chamador deixar uma mensagem de voz

 

_**Aplica-se a:** Exchange Online, Exchange Server 2013, Exchange Server 2016_

_**Tópico modificado em:** 2013-02-22_

Você pode permitir que usuários habilitados para UM recebam mensagens de voz de chamadores anônimos ou impedi-los de fazer isso. Por padrão, quando os usuários estão habilitados para Unificação de Mensagens (UM) e mensagens de voz, eles podem receber chamadas anônimas que não contenham informações de identificação de chamadas.

Na maioria dos casos, as chamadas recebidas por UM contêm uma ID de chamadas que pode ser usado para determinar a origem da chamada de entrada. Entretanto, as chamadas de entrada podem não incluir as informações de ID de chamadas pelos seguintes motivos:

  - O equipamento de telefonia da sua organização está configurado para não incluir as informações de ID de chamada.

  - A chamada de entrada foi originada de um telefone externo ou celular.

  - O chamador desabilitou o ID de chamada no seu telefone.

Como o parâmetro *AnonymousCallersCanLeaveMessages* é habilitado por padrão, um usuário habilitado para UM pode receber uma mensagem de voz mesmo se a informação de identificação da chamada não estiver incluída. Se a opção *AnonymousCallersCanLeaveMessages* estiver desabilitada e o usuário habilitado para UM receber uma chamada que não inclua uma identificação de chamada, a chamada será identificada como anônima e o usuário habilitado para UM não receberá a mensagem de voz.

Para conhecer tarefas de gerenciamento adicionais relacionadas a usuários habilitados para caixa postal, consulte [Procedimentos do usuário habilitado para email de voz](voice-mail-enabled-user-procedures-exchange-2013-help.md).

## O que você precisa saber antes de começar?

  - Tempo estimado para conclusão: 2 minutos.

  - Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Caixas de correio da UM" no tópico [Permissões de mensagens unificadas](unified-messaging-permissions-exchange-2013-help.md).

  - Antes de executar esse procedimento, verifique se um plano de discagem de UM foi criado. Para obter etapas detalhadas, consulte [Criar um plano de discagem de UM](create-a-um-dial-plan-exchange-2013-help.md).

  - Antes de executar esse procedimento, verifique se uma política de caixa de correio de UM foi criado. Para conhecer etapas detalhadas, consulte [Criar uma política de caixa de correio da UM](create-a-um-mailbox-policy-exchange-2013-help.md).

  - Antes de você executar esse procedimento, verifique se a caixa de correio de usuário foi habilitada para UM. Para conhecer etapas detalhadas, consulte [Habilitar um usuário para caixa postal](enable-a-user-for-voice-mail-exchange-2013-help.md).

  - Para informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, consulte [Atalhos de teclado no Centro de administração do Exchange](keyboard-shortcuts-in-the-exchange-admin-center-exchange-online-protection-help.md).


> [!TIP]
> Está enfrentando problemas? Peça ajuda nos fóruns do Exchange. Visite os fóruns em: <A href="https://go.microsoft.com/fwlink/p/?linkid=60612">Exchange Server</A>, <A href="https://go.microsoft.com/fwlink/p/?linkid=267542">Exchange Online</A>, ou <A href="https://go.microsoft.com/fwlink/p/?linkid=285351">Proteção do Exchange Online</A>..



## Usar o Shell para permitir que mensagens de voz de chamadas anônimas sejam recebidas

Este exemplo permite que o usuário habilitado para UM tonysmith@contoso.com receba mensagens de voz de chamadas que não contenham a informação de identificação de chamadas.

    Set-UMMailbox -Identity tonysmith@contoso.com -AnonymousCallersCanLeaveMessages $true

