---
title: "Ladění aplikací ClickOnce používajících System.Deployment.Application | Microsoft Docs"
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
- ClickOnce deployment, debugging
- debugging, ClickOnce applications
- debugging, System.Deployment
- deploying applications [ClickOnce], debugging
ms.assetid: 86f31948-2ca8-47c0-8e8b-c2b817bbf79f
caps.latest.revision: "14"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: cc4d2a778449be4cbb441397c0a5a427ef91e8dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-clickonce-applications-that-use-systemdeploymentapplication"></a>Ladění aplikací ClickOnce používajících System.Deployment.Application
V [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení můžete konfigurovat, jak je aktualizovat aplikaci. Ale pokud budete muset používat a přizpůsobit pokročilé [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení funkce, potřebujete pro přístup k modelu objektu nasazení poskytované <xref:System.Deployment.Application>. Můžete použít <xref:System.Deployment.Application> rozhraní API pro pokročilé úlohy, jako:  
  
-   Vytváření v aplikaci možnost "Aktualizovat teď"  
  
-   Stažení na vyžádání podmíněného, z různých součástí aplikace  
  
-   Aktualizace integrované přímo do aplikace  
  
-   Zaručit, že klientská aplikace je vždy aktuální  
  
 Protože <xref:System.Deployment.Application> rozhraní API fungovat pouze, když je aplikace nasazená s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] technologie, je jediným způsobem, jak je ladění pro nasazení aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], k němu připojí a následné ladění. Může být obtížné připojit ladicí program dostatečně včas, protože tento kód často spustí, když se aplikace spouští a provede předtím, než je možné připojit ladicí program. Řešení je umístění přerušení (nebo zastaví pro projekty Visual Basic) před aktualizace zkontrolujte kód nebo kód na vyžádání.  
  
 Doporučená technika ladění je následující:  
  
1.  Než začnete, ujistěte se, že symbolu (.pdb) a zdrojové soubory jsou archivovány.  
  
2.  Nasazení 1 verzi aplikace.  
  
3.  Vytvoření nové prázdné řešení. Z **soubor** nabídky, klikněte na tlačítko **nový**, pak **projektu**. V **nový projekt** dialogové okno, otevřete **jiné typy projektů** uzlu, pak vyberte **řešení sady Visual Studio** složky. V **šablony** podokně, vyberte **prázdného řešení**.  
  
4.  Přidejte archivované zdrojové umístění pro vlastnosti pro toto nové řešení. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a pak klikněte na tlačítko **vlastnosti**. V **stránky vlastností** dialogové okno, vyberte **zdrojové soubory ladění**, pak přidejte adresář archivovaného zdrojového kódu. Ladicí program, jinak hodnota zjistí zastaralé zdrojové soubory, protože zdrojové cesty k souborům se zaznamenávají do souboru pdb. Ladicí program používá zastaralé zdrojové soubory, zobrazí se zpráva, která neodpovídá zdroji.  
  
5.  Zajistěte, aby že ladicí program můžete najít soubory PDB. Pokud jste je nasadili s vaší aplikací, ladicí program vyhledá je automaticky. Vždy vypadá vedle sestavení v první. Jinak, budete muset přidat cestu k archivu do **symbolů umístění souborů (.pdb)** (pro přístup k této možnosti z **nástroje** nabídky, klikněte na tlačítko **možnosti**, otevřete  **Ladění** uzel a klikněte na tlačítko **symboly**).  
  
6.  Ladění, co se stane, že mezi `CheckForUpdate` a `Download` / `Update` volání metody.  
  
     Kód aktualizace může být například takto:  
  
    ```  
        Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
            If My.Application.Deployment.IsNetworkDeployed Then  
  
                If (My.Application.Deployment.CheckForUpdate()) Then  
  
                    My.Application.Deployment.Update()  
                    Application.Restart()  
  
                End If  
  
            End If  
        End Sub  
    ```  
  
7.  Nasazení verze 2.  
  
8.  Pokuste se připojit ladicí program k aplikaci verze 1 během stahování aktualizace pro verze 2. Případně můžete použít `System.Diagnostics.Debugger.Break` metoda nebo jednoduše `Stop` v jazyce Visual Basic. Samozřejmě by neměl ponechat volání této metody v produkčním kódu.  
  
     Předpokládejme například, vyvíjíte aplikace Windows Forms a máte obslužné rutiny události pro tuto metodu s logiku aktualizace ve frontě. Chcete-li ladit tento, jednoduše připojte před tlačítko stisknutí a potom nastavit zarážky (ujistěte se, otevřete odpovídající archivovaný soubor a nastavili zde zarážku).  
  
 Použití <xref:System.Deployment.Application.ApplicationDeployment.IsNetworkDeployed%2A> vlastnost má být vyvolán <xref:System.Deployment.Application> rozhraní API jenom v případě, že je aplikace nasazená; rozhraní API by neměla být volána během ladění v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Deployment.Application>