---
title: "Postupy: povolení nastavení zabezpečení ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: d9fb07f8348e161743b373a83d49c4dd614d8c5f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-clickonce-security-settings"></a>Postupy: Povolení nastavení zabezpečení ClickOnce
Chcete-li publikovat aplikace musí být povoleno zabezpečení přístupu kódu pro aplikace ClickOnce. To se provádí automaticky při publikování aplikace pomocí Průvodce publikování.  
  
 V některých případech může povolení zabezpečení přístupu kódu ovlivnit výkon při vytváření nebo ladění aplikace; v těchto případech můžete chtít dočasně zakázat nastavení zabezpečení.  
  
 Nastavení zabezpečení ClickOnce můžete povolit nebo zakázat na **zabezpečení** stránky **Návrhář projektu**.  
  
### <a name="to-enable-clickonce-security-settings"></a>Chcete-li povolit nastavení zabezpečení ClickOnce  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **zabezpečení** kartě.  
  
3.  Vyberte **povolení nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
     Nyní můžete přizpůsobit nastavení zabezpečení pro vaši aplikaci na stránce zabezpečení.  
  
    > [!NOTE]
    >  Toto zaškrtávací políčko se vybere automaticky pokaždé, když je aplikace publikována s **publikovat** průvodce.  
  
### <a name="to-disable-clickonce-security-settings"></a>Chcete-li zakázat nastavení zabezpečení ClickOnce  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **zabezpečení** kartě.  
  
3.  Vymazat **povolení nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
     Vaše aplikace spustí s nastavením zabezpečení úplný vztah důvěryhodnosti; všechna nastavení na **zabezpečení** stránky budou ignorovány.  
  
    > [!NOTE]
    >  Pokaždé, když je aplikace publikována pomocí Průvodce publikováním, toto zaškrtávací políčko bude vybrána; je třeba ji zrušit znovu po každém úspěšném publikování.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 
