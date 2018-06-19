---
title: 'Postupy: určení souborů k publikování aplikací ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.File
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, file exclusion
- files, publishing via ClickOnce
ms.assetid: 579c134a-d50f-4e0c-8e05-2a4ff654896a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c59ffc2324f25c42b505505b0dbea9160ef023a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31561412"
---
# <a name="how-to-specify-which-files-are-published-by-clickonce"></a>Postupy: Určení souborů k publikování aplikací ClickOnce
Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, všechny kód soubory v projektu nasazených spolu s aplikací. V některých případech nechcete nebo třeba určité soubory nebo můžete chtít nainstalovat určité soubory na základě podmínek. Visual Studio poskytuje možnosti, které chcete vyloučit soubory, soubory označit jako datové soubory nebo požadavky a vytvoření skupin souborů pro podmíněnou instalaci.  
  
 Soubory [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se spravují v **soubory aplikace** dialogové okno, přístupný ze **publikovat** stránky **Návrhář projektu**.  
  
 Standardně je skupina jednoho souboru s názvem **(povinné)**. Můžete vytvořit další skupiny souborů a k nim přiřadíte soubory. Nelze změnit **Skupina stažení** pro soubory, které jsou požadovány pro spuštění aplikace. Například aplikace .exe nebo soubory označené jako datové soubory, musí patřit do **(povinné)** skupiny.  
  
 Stav publikování výchozí hodnota je označené hodnotou soubor **(automaticky)**. Například .exe aplikace má stav publikování **zahrnout (automaticky)** ve výchozím nastavení.  
  
 Soubory s **akce sestavení** vlastnost nastavena na hodnotu **obsahu** jsou označeny jako soubory aplikace a bude označená jako zahrnuté ve výchozím nastavení. Může být zahrnout, vyloučit nebo označené jako data. Výjimky jsou následující:  
  
-   Datové soubory, jako jsou soubory databáze SQL (MDF a .mdb) a soubory XML budou označeny jako datové soubory ve výchozím nastavení.  
  
-   Odkazy na sestavení (soubory .dll), jsou určené následujícím způsobem, když přidáte odkaz: Pokud **místní kopie** je **False**, je označen ve výchozím nastavení jako požadované sestavení (**požadovaných ( Automatické)**), musí existovat v mezipaměti GAC předtím, než se aplikace nainstaluje. Pokud **místní kopie** je **True**, sestavení se standardně jako sestavení aplikace (**zahrnout (automaticky)**) a budou zkopírovány do složky aplikace během instalace. COM odkaz se zobrazí v **soubory aplikace** dialogové okno pole (jako soubor .ocx) pouze v případě jeho **izolovaná** je nastavena na **True**. Ve výchozím nastavení bude součástí.  
  
### <a name="to-add-files-to-the-application-files-dialog-box"></a>Chcete-li přidat soubory do dialogového okna soubory aplikace  
  
1.  Vyberte soubor dat v **Průzkumníku řešení**.  
  
2.  V okně vlastností změňte **akce sestavení** vlastnost, která má **obsahu** hodnotu.  
  
### <a name="to-exclude-files-from-clickonce-publishing"></a>Vyloučení souborů ze publikování ClickOnce  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **soubory aplikace** tlačítko Otevřít **soubory aplikace** dialogové okno.  
  
4.  V **soubory aplikace** dialogové okno, vyberte soubor, který chcete vyloučit.  
  
5.  V **stav publikování** pole, vyberte **vyloučit** z rozevíracího seznamu.  
  
### <a name="to-mark-files-as-data-files"></a>K označení souborů jako datové soubory  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **soubory aplikace** tlačítko Otevřít **soubory aplikace** dialogové okno.  
  
4.  V **soubory aplikace** dialogové okno, vyberte soubor, který chcete označit jako data.  
  
5.  V **stav publikování** pole, vyberte **datový soubor** z rozevíracího seznamu.  
  
### <a name="to-mark-files-as-prerequisites"></a>K označení souborů jako požadavky  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **soubory aplikace** tlačítko Otevřít **soubory aplikace** dialogové okno.  
  
4.  V **soubory aplikace** dialogovém okně vyberte sestavení aplikace (soubor .dll), které chcete označit jako předpoklad. Všimněte si, že vaše aplikace musí mít odkaz na sestavení aplikace v pořadí pro zobrazí v seznamu.  
  
5.  V **stav publikování** pole, vyberte **požadovaných** z rozevíracího seznamu.  
  
### <a name="to-add-a-new-file-group"></a>Chcete-li přidat novou skupinu souborů  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **soubory aplikace** tlačítko Otevřít **soubory aplikace** dialogové okno.  
  
4.  V **soubory aplikace** dialogové okno, vyberte **skupiny** pole pro soubor, který chcete zahrnout do nové skupiny.  
  
    > [!NOTE]
    >  Soubory musí mít **akce sestavení** vlastnost nastavena na hodnotu **obsahu** názvy souborů se v **soubory aplikace** dialogové okno.  
  
5.  V **Skupina stažení** pole, vyberte  **\<nová... >** z rozevíracího seznamu.  
  
6.  V **nová skupina** dialogové okno, zadejte název skupiny a pak klikněte na tlačítko **OK**.  
  
### <a name="to-add-a-file-to-a-group"></a>Přidání souboru do skupiny  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **soubory aplikace** tlačítko Otevřít **soubory aplikace** dialogové okno.  
  
4.  V **soubory aplikace** dialogové okno, vyberte **skupiny** pole pro soubor, který chcete zahrnout do nové skupiny.  
  
5.  V **Skupina stažení** pole, vyberte skupinu z rozevíracího seznamu.  
  
    > [!NOTE]
    >  Nelze změnit **Skupina stažení** pro soubory, které jsou požadovány pro spuštění aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)