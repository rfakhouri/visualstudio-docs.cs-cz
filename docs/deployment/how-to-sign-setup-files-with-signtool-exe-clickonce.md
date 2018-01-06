---
title: "Postupy: podepsání souborů instalace pomocí SignTool.exe (ClickOnce) | Microsoft Docs"
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
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 38fec52a9ca4c152a8bb1065e2d33aa1ea52c97f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>Postupy: Podepsání souborů instalace pomocí SignTool.exe (ClickOnce)
SignTool.exe můžete použít k podepsání instalačního programu (setup.exe). Tento proces zajišťuje, že nejsou nainstalovány zmanipulovanou soubory na počítačích koncových uživatelů.  
  
 Ve výchozím nastavení má ClickOnce podepsané manifesty a podepsaný instalační program. Ale pokud chcete změnit parametry instalační program později, musíte se odhlásit instalační program později. Pokud změníte parametry, až instalační program je podepsaný, dojde k poškození podpis.  
  
 Následující postup vytvoří nepodepsané manifesty a nepodepsaný instalační program. Pak je ke generování podepsané manifesty v sadě Visual Studio podepisování ClickOnce povoleno. Instalační program je ponechán bez znaménka, aby zákazník mohli podepsat spustitelný soubor s svůj vlastní certifikát.  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>Pro generování nepodepsaného instalačního programu a podepsání později  
  
1.  Na vývojovém počítači, nainstalujte certifikát, který má přihlašovací manifesty s.  
  
2.  Vyberte projekt v **Průzkumníku řešení**.  
  
3.  Na **projektu** nabídky, klikněte na tlačítko *ProjectName* **vlastnosti**.  
  
4.  V **podpisování** zrušte zaškrtnutí políčka **podepsání manifestů ClickOnce**.  
  
5.  V **publikovat** klikněte na tlačítko **požadavky**.  
  
6.  Ověřte, zda jsou vybrané všechny předpoklady a pak klikněte na tlačítko **OK**.  
  
7.  V **publikovat** stránky, ověřte nastavení publikování a pak klikněte na tlačítko **publikovat**.  
  
     Řešení publikuje nepodepsaný manifest aplikace, manifest nasazení bez znaménka, soubory specifické pro verzi a nepodepsaný instalační program k publikování umístění složky.  
  
8.  V **publikovat** klikněte na tlačítko **požadavky**.  
  
9. V **požadavky** dialogové okno, zrušte zaškrtnutí **vytvořit instalační program pro instalaci požadovaných součástí**.  
  
10. V **publikovat** stránky, ověřte nastavení publikování a pak klikněte na tlačítko **publikovat**.  
  
     Řešení publikuje podepsaný manifest aplikace, manifest podepsaný nasazení a soubory specifické pro verzi publikování umístění složky. Proces publikování není přepsány nepodepsaný instalační program.  
  
11. Na straně zákazníka otevřete příkazový řádek.  
  
12. Přejděte do adresáře, který obsahuje soubor .exe.  
  
13. Podepsání souboru .exe pomocí následujícího příkazu:  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     Například k podepsání instalačního programu, použijte jednu z následujících příkazů:  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Opětovné podepisování manifestů aplikace a nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md)