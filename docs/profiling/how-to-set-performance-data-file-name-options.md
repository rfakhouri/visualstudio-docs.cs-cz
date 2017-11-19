---
title: "Postupy: nastavení možností názvu datového souboru výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 308766c1a4fbe5194f1330bd74c81f6d9d41b36f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-set-performance-data-file-name-options"></a>Postupy: nastavení možností názvu datového souboru výkonu
Ve výchozím nastavení uložte soubor profilování dat (.vsp) pomocí následující syntaxe:  
  
 *Path\VSP-File\YYMMDD(N)* **.vsp**  
  
 Pro relaci, výkon, můžete změnit libovolný pojmenování parametr na stránce Obecné v dialogovém okně Vlastnosti.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
|||  
|-|-|  
|*Cesta*|Adresář, který obsahuje sestavu. Výchozí umístění je složka řešení nebo výchozí umístění pro projekty a řešení pro uživatele.|  
|*VSP – soubor*|Název datového souboru profilování. Výchozí název je název řešení nebo spustitelného souboru, je profilovaným.|  
|*RRMMDD*|Razítka data, který ukazuje rok, měsíc a den, která nebyla shromážděna profilování data.|  
|*(NE)*|Pokud existuje více než jeden profilování datový soubor, zvýšena číslo se přidá k názvu souboru mezi závorky.|  
  
### <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Chcete-li změnit pojmenování syntaxe datových souborů profilace výkonnostní relace  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na název výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **Obecné**.  
  
3.  V části **sestavy**, změnit následující nastavení:  
  
    |||  
    |-|-|  
    |**Umístění sestavy**|Zadejte adresář pro ukládání datových souborů profilování.|  
    |**Název sestavy**|Zadejte základní název pro soubory.|  
    |**Automaticky přidat nové sestavy do relace**|Zaškrtněte políčko automaticky přidat do relace výkon datového souboru.|  
    |**Připojit narůstajícími číslo generované sestav**|Zaškrtněte políčko Přidat narůstajícími číslo k názvu souboru, pokud existuje více než jeden soubor se stejným názvem. Zrušte zaškrtnutí políčka Přepsat existující soubor.|  
    |**Používat časové razítko pro číslo**|Zaškrtněte políčko Přidat datestamp k názvu souboru.|