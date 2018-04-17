---
title: 'Postupy: povolení nastavení zabezpečení ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5c59786a49f09efd2dc4d906511ac2602c765c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 
