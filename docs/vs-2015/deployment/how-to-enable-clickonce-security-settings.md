---
title: 'Postupy: Povolení nastavení zabezpečení ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1b104a7a0451da7f772077d2f566b36b9f601c17
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63433808"
---
# <a name="how-to-enable-clickonce-security-settings"></a>Postupy: Povolení nastavení zabezpečení ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li publikovat aplikace musí být povoleno zabezpečení přístupu ke kódu pro aplikace ClickOnce. To se provádí automaticky při publikování aplikace pomocí Průvodce publikováním.  
  
 V některých případech povolení zabezpečení přístupu kódu může mít vliv na výkon při sestavování nebo ladění aplikace; v těchto případech můžete chtít dočasně zakázat nastavení zabezpečení.  
  
 Nastavení zabezpečení ClickOnce můžete povolit nebo zakázat na **zabezpečení** stránku **Návrháře projektu**.  
  
### <a name="to-enable-clickonce-security-settings"></a>Povolení nastavení zabezpečení ClickOnce  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. Klikněte na tlačítko **zabezpečení** kartu.  
  
3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
     Teď můžete přizpůsobit nastavení zabezpečení pro vaši aplikaci na stránce zabezpečení.  
  
    > [!NOTE]
    > Toto zaškrtávací políčko je zaškrtnuto automaticky pokaždé, když je aplikace publikována s **publikovat** průvodce.  
  
### <a name="to-disable-clickonce-security-settings"></a>Chcete-li zakázat nastavení zabezpečení ClickOnce  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. Klikněte na tlačítko **zabezpečení** kartu.  
  
3. Zrušte **povolit nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
     Vaše aplikace bude spuštěna pomocí nastavení zabezpečení úplný vztah důvěryhodnosti. všechna nastavení **zabezpečení** stránky se bude ignorovat.  
  
    > [!NOTE]
    > Pokaždé, když je aplikace publikována pomocí Průvodce publikováním toto zaškrtávací políčko bude vybrána; je třeba ji zrušit po každém úspěšném publikování.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
