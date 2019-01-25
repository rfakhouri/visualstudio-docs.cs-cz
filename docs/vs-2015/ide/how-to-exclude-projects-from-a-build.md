---
title: 'Postupy: Vyloučení projektů ze sestavení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 04a3a45af932a34b89feb2726e7a137ceea2ac5a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780123"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Postupy: Vyloučení projektů ze sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vytvoření řešení bez nutnosti všechny projekty, které obsahuje. Například může vyloučit projektu, který naruší sestavení. Může pak sestavíte projekt po můžete prozkoumat a adresu problémy.  
  
 Projekt můžete vyloučit pomocí následujících postupů:  
  
- Odstraněním dočasně konfiguraci aktivního řešení.  
  
- Vytvoření konfigurace řešení, která neobsahuje projekt.  
  
  Další informace najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>K dočasnému odstranění projektu z konfigurace aktivního řešení  
  
1.  V panelu nabídky zvolte **sestavení**, **nástroje Configuration Manager**.  
  
2.  V **projektu kontexty** tabulky, najděte projektu, které chcete vyloučit ze sestavení.  
  
3.  V **sestavení** sloupec pro projekt, zrušte zaškrtnutí políčka.  
  
4.  Zvolte **Zavřít** tlačítko a pak znovu sestavte řešení.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Pro vytvoření konfigurace řešení, která nezahrnuje projektu  
  
1.  V panelu nabídky zvolte **sestavení**, **nástroje Configuration Manager**.  
  
2.  V **konfigurace aktivního řešení** klikněte na položku  **\<nový >**.  
  
3.  V **název** pole, zadejte název konfigurace řešení.  
  
4.  V **Kopírovat nastavení z:** klikněte na položku konfigurace řešení, na kterém chcete vytvořit novou konfiguraci (například **ladění**) a klikněte na tlačítko **OK** tlačítko .  
  
5.  V **nástroje Configuration Manager** dialogové okno, zrušte zaškrtnutí políčka v **sestavení** sloupec pro projekt, který chcete vyloučit a klikněte na tlačítko **Zavřít** tlačítko.  
  
6.  Na **standardní** nástrojů, ověřte, zda je nová konfigurace řešení v aktivní konfiguraci **konfigurace řešení** pole.  
  
7.  V panelu nabídky zvolte **sestavení**, **znovu sestavit řešení**.  
  
## <a name="see-also"></a>Viz také  
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Postupy: Sestavení více konfigurací současně](../ide/how-to-build-multiple-configurations-simultaneously.md)
