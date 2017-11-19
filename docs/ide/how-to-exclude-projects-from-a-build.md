---
title: "Postupy: vyloučení projektů ze sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 64a10c356100e6ace36ec1c574c85479741113c8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-exclude-projects-from-a-build"></a>Postupy: Vyloučení projektů ze sestavení
Můžete vytvořit řešení bez vytváření všechny projekty, které obsahuje. Například může vyloučit projekt, který dělí sestavení. Je pak sestavení projektu po byste prozkoumat a adresu problémy.  
  
 Pomocí následujících postupů můžete vyloučit projektu:  
  
-   Odstraněním dočasně konfigurace aktivního řešení.  
  
-   Vytvoření konfigurace řešení, která neobsahuje projekt.  
  
 Další informace najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Dočasně odebrání konfigurace aktivního řešení projektu  
  
1.  Na řádku nabídek zvolte **sestavení**, **nástroje Configuration Manager**.  
  
2.  V **projektu kontexty** tabulky, vyhledejte projektu, které chcete vyloučit z buildu.  
  
3.  V **sestavení** sloupce projektu, zrušte zaškrtnutí políčka.  
  
4.  Vyberte **Zavřít** tlačítko a pak znovu sestavte řešení.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Pro vytvoření konfigurace řešení, které vylučuje projektu  
  
1.  Na řádku nabídek zvolte **sestavení**, **nástroje Configuration Manager**.  
  
2.  V **aktivní konfigurace řešení** vyberte  **\<nový >**.  
  
3.  V **název** pole, zadejte název pro konfiguraci řešení.  
  
4.  V **Kopírovat nastavení z** vyberte konfigurace řešení, na kterém chcete vytvořit novou konfiguraci (například **ladění**) a potom zvolte **OK** tlačítko .  
  
5.  V **nástroje Configuration Manager** dialogové okno, zrušte zaškrtnutí políčka v **sestavení** sloupec pro projekt, který chcete vyloučit a potom vyberte **Zavřít** tlačítko.  
  
6.  Na **standardní** nástrojů ověřte, zda se nová konfigurace řešení je aktivní konfigurace v **konfigurace řešení** pole.  
  
7.  Na řádku nabídek zvolte **sestavení**, **znovu sestavit řešení**.  
  
## <a name="see-also"></a>Viz také  
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Postupy: sestavení více konfigurací současně](../ide/how-to-build-multiple-configurations-simultaneously.md)