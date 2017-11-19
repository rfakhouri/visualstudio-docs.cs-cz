---
title: "Ostatní soubory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.newfile
- VS.OpenWith
- MiscellaneousFilesProject
helpviewer_keywords:
- solutions, miscellaneous files
- builds [Visual Studio], miscellaneous files
- standalone files
- Solution Explorer, miscellaneous files
- Miscellaneous Files folder
- files [Visual Studio], outside of containers
- files [Visual Studio], Miscellaneous Files folder
ms.assetid: 5b96640b-8efe-48a4-8d0a-1ae3f9587e44
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 831d0f60c992324c81cb1366ac28b3e3f1b066ad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="miscellaneous-files"></a>Ostatní soubory
Můžete chtít použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] editory pracovat nezávisle na soubory z projektu nebo řešení. Při řešení otevřené, můžete otevřít a upravit soubory bez jejich přidáním do řešení nebo do projektu. Soubory, které chcete pracovat nezávisle z kontejnerů se nazývají různé soubory. Ostatní soubory jsou externí vzhledem k řešení a projekty, nejsou zahrnuty v sestavení a nemůže být součástí řešení ve správě zdrojového kódu.  
  
 Otevírání souborů nezávisle z kontejneru je vhodné pro celou řadu důvodů. Můžete mít soubor, který chcete zobrazit při vývoji řešení pro projekt ale není nezbytný pro vývoj řešení. Běžné mezi příklady patří vývoj poznámky nebo pokyny, schéma databáze a klipů kódu. Kromě toho můžete chtít vytvořit samostatný soubor.  
  
 ![Projekty řešení](../../ide/reference/media/projects_solutions_misc.gif "Projects_Solutions_Misc")  
  
 Průzkumník řešení může zobrazit složku různé soubory pro soubory, pokud jsou povolené možnosti složky. Možnosti můžete nastavit [dokumenty, prostředí, dialogové okno Možnosti](../../ide/reference/documents-environment-options-dialog-box.md). Když zavřete soubor různé, není přidružený žádné konkrétní řešení nebo produktu project Pokud možnost je povolen také pro tento.  
  
 Složka pro různé soubory představuje soubory jako odkazy. I když tato složka není součástí řešení, když otevřete řešení, některé nebo všechny ostatní soubory, které byly otevřeny při posledním zavření řešení jsou znovu otevřít, v závislosti na nastavení pro danou složku.  
  
> [!NOTE]
>  Některé soubory, které nejsou uvedeny ve složce různé soubory jsou .doc soubory a soubory, které nelze změnit v prostředí IDE, jako jsou soubory .zip. Prostředí IDE nebude sledovat soubory, které můžete upravit pouze pomocí externího editoru.  
  
## <a name="commands-available-in-the-ide"></a>Příkazy, které jsou k dispozici v prostředí IDE  
 V nabídkách, panely nástrojů a příkazy obsahují změnu na základě formátu souboru otevřete. Když otevřete textový soubor, například zobrazí panel nástrojů textovém editoru a jeho příkazy jsou k dispozici. Pokud pak otevřít soubor schématu XML, zobrazí se panel nástrojů schématu XML. Při úpravách schématu XML, nejsou k dispozici příkazy textového editoru panelu nástrojů (nebo samotný panel nástrojů). Schéma XML je aktivní okno a jako takový má kontext aktuálního výběru. Při přepínání mezi soubor projektu a soubor různé zmizí všechny příkazy související s projektem a zobrazí pouze ty, které jsou přímo souvisí s různým souboru.  
  
## <a name="folder-display-options"></a>Možnosti zobrazení složky  
 Možnosti zobrazení pro různé složky můžete nastavit tak, aby složka se zobrazí, i když nejsou otevřené žádné různé soubory. Soubor řešení trvale nespravuje seznam různé soubory. Používá volitelnou funkci, která umožňuje mějte na paměti, uživatelská naposledy použité (naposledy použitých) seznam souborů.  
  
## <a name="see-also"></a>Viz také  
 [Projekty a řešení](../../ide/solutions-and-projects-in-visual-studio.md)   
 [Dokumenty, prostředí, dialogové okno Možnosti](../../ide/reference/documents-environment-options-dialog-box.md)