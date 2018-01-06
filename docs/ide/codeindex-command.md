---
title: "Codeindex – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command-line tools [Team Foundation Server]
- TFSConfig
- CodeIndex command [Team Foundation Server]
ms.assetid: b79568d4-6a64-4ca9-a1ee-3e57f92a9c5c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3f181dccce6239cc8014e8e8ebf54c2e53794a50
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="codeindex-command"></a>CodeIndex – příkaz
Použití **codeindex –** příkaz ke správě kódu indexování na Team Foundation Server. Například můžete chtít obnovit index pro opravu Codelensu informace nebo vypnout indexování prozkoumat problémy s výkonem serveru.  
  
 **Požadovaná oprávnění**  
  
 Použít **codeindex –** příkaz, musíte být členem skupiny **Team Foundation správci** skupiny zabezpečení. V tématu [oprávnění a skupiny, které jsou definovány pro Team Services a sady TFS](https://www.visualstudio.com/docs/setup-admin/permissions).  
  
> [!NOTE]
>  I v případě, že přihlášení s přihlašovacími údaji správce, musíte otevřít okno příkazového řádku se zvýšenými oprávněními ke spuštění tohoto příkazu. Tento příkaz musí spustit také z vrstvy aplikace pro produkt Team Foundation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
TFSConfig CodeIndex /indexingStatus | /setIndexing:[ on | off | keepupOnly ] | /ignoreList:[ add | remove | removeAll | view ] ServerPath | /listLargeFiles [/fileCount:FileCount] [/minSize:MinSize] | /reindexAll | /destroyCodeIndex [/noPrompt] | /temporaryDataSizeLimit:[ view | <SizeInGBs> | disable ] | /indexHistoryPeriod:[ view | all | <NumberOfMonths> ] [/collectionName:CollectionName | /collectionId:CollectionId]  
```  
  
#### <a name="parameters"></a>Parametry  
  
|**Argument**|**Popis**|  
|------------------|---------------------|  
|`CollectionName`|Určuje název kolekce týmového projektu. Pokud název obsahuje mezery, uzavřete název v uvozovkách, například "Fabrikam webový server".|  
|`CollectionId`|Určuje identifikační číslo kolekce týmového projektu.|  
|`ServerPath`|Určuje cestu k souboru kódu.|  
  
|**Možnost**|**Popis**|  
|----------------|---------------------|  
|**/indexingStatus**|Zobrazení stavu a konfiguraci služby indexování kódu.|  
|**/setIndexing:**[na &#124; vypnutí &#124; keepupOnly]|-   **na**: spuštění indexování všech změn.<br />-   **vypnout**: Zastavit indexování všech změn.<br />-   **keepupOnly**: Zastavit indexování dříve vytvořenou změn a spustit indexování pouze nové sady změn.|  
|**/ignoreList:**[Přidat &#124; odebrat &#124; removeAll &#124; zobrazení]`ServerPath`<br /><br /> Při spuštění, end nebo oba konce cestu na serveru, můžete použít zástupný znak (*).|Určuje seznam soubory kódu a jejich cesty, které nechcete použít indexované.<br /><br /> -   **Přidat**: přidání souboru, který nechcete, aby indexována, aby seznam ignorovaných souborů.<br />-   **Odebrat**: odstranění souboru, který chcete indexované ze seznamu ignorovaných souboru.<br />-   **removeAll**: Vymazat seznam ignorovaných souborů a začít indexování všechny soubory.<br />-   **zobrazení**: Zobrazit všechny soubory, které nejsou probíhá indexování.|  
|**/listLargeFiles [/ fileCount:** `FileCount` **/minSize:** `MinSize`]|Zobrazuje zadaný počet souborů, který je delší než zadaná velikost v KB. Pak můžete použít **/ignoreList** možnost vyloučit tyto soubory z indexování.|  
|**/reindexAll**|Vymažte dříve indexovaná data a restartujte indexování.|  
|**/destroyCodeIndex [/noPrompt]**|Odstranit kód index a odeberte všechny indexovaná data. Nevyžaduje potvrzení, pokud použijete **/noPrompt** možnost.|  
|**/temporaryDataSizeLimit**: [zobrazení &#124; <`SizeInGBs`> &#124; zakázat]|Určit, kolik dočasná data, která vytvoří Codelensu při zpracování změn. Výchozí limit je 2 GB.<br /><br /> -   **zobrazení**: Zobrazit aktuální limit velikosti.<br />-   `SizeInGBs`: Změňte omezení velikosti.<br />-   **Zakázat**: odeberte omezení velikosti.<br /><br /> Tento limit je zaškrtnuta možnost než Codelensu zpracuje novou sadu změn. Pokud dočasná data, která překračuje tento limit, bude Codelensu pozastavit zpracování po sady změn, není nové. Codelensu se restartuje po dat je vyčištěna a klesne pod tento limit zpracování. Čištění se spustí automaticky jednou denně. To znamená, že dočasná data, která může překročí toto omezení, dokud nebude vyčištění spuštění.|  
|**/indexHistoryPeriod**: [zobrazení &#124; všechny &#124; <`NumberOfMonths`>]|Ovládací prvek, jak dlouho chcete indexu historii změn. To ovlivní, kolik historie Codelensu ukazuje. Výchozí limit je 12 měsíců. To znamená Codelensu Zobrazí historii změn z jenom za posledních 12 měsíců.<br /><br /> -   **zobrazení**: Zobrazit aktuální počet měsíců.<br />-   **všechny**: Index veškerou historii změn.<br />-   `NumberOfMonths`: Počet měsíců, používá k historii změn index změňte.|  
|**/collectionName:**`CollectionName`|Určuje název kolekce týmového projektu, na který se má spustit **codeindex –** příkaz. Vyžaduje, pokud nepoužíváte **/CollectionId**.|  
|**/collectionId:**`CollectionId`|Určuje identifikační číslo kolekce týmového projektu, na který se má spustit **codeindex –** příkaz. Vyžaduje, pokud nepoužíváte **/CollectionName**.|  
  
## <a name="examples"></a>Příklady  
  
> [!NOTE]
>  Příklady společností, organizací, produktů, názvů domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené.  Žádné spojení se skutečnou společností, organizace, produktu, název domény, e-mailovou adresu, logem, osoba, místech nebo události je určený nebo událostmi.  
  
 Pokud chcete zobrazit kód indexování stavu a konfiguraci:  
  
```  
TFSConfig CodeIndex /indexingStatus /collectionName:"Fabrikam Web Site"  
```  
  
 Spuštění indexování všech změn:  
  
```  
TFSConfig CodeIndex /setIndexing:on /collectionName:"Fabrikam Web Site"  
```  
  
 Zastavení indexování dříve vytvořenou změn a spustit indexování pouze nové změn:  
  
```  
TFSConfig CodeIndex /setIndexing:keepupOnly /collectionName:"Fabrikam Web Site"  
```  
  
 Vyhledání až 50 souborů, které jsou větší než 10 KB:  
  
```  
TFSConfig CodeIndex /listLargeFiles /fileCount:50 /minSize:10 /collectionName:"Fabrikam Web Site"  
```  
  
 Vyloučit konkrétní soubor z indexování a přidejte do seznamu ignorovaných souboru:  
  
```  
TFSConfig CodeIndex /ignoreList:add "$/Fabrikam Web Site/Catalog.cs" /collectionName:"Fabrikam Web Site"  
```  
  
 Pokud chcete zobrazit všechny soubory, které nejsou indexovány:  
  
```  
TFSConfig CodeIndex /ignoreList:view  
```  
  
 Zrušte dříve indexovaná data a restartujte indexování:  
  
```  
TFSConfig CodeIndex /reindexAll /collectionName:"Fabrikam Web Site"  
```  
  
 Uložte veškerá historie změn:  
  
```  
TFSConfig CodeIndex /indexHistoryPeriod:all /collectionName:"Fabrikam Web Site"  
```  
  
 Odeberte limit velikosti na Codelensu dočasná data a pokračovat indexování bez ohledu na velikost dočasná data:  
  
```  
TFSConfig CodeIndex /temporaryDataSizeLimit:disable /collectionName:"Fabrikam Web Site"  
```  
  
 Chcete-li odstranit kód index s potvrzení:  
  
```  
TFSConfig CodeIndex /destroyCodeIndex /collectionName:"Fabrikam Web Site"  
```  
  
## <a name="see-also"></a>Viz také

[Nalezení změn kódu a další historie pomocí CodeLensu](../ide/find-code-changes-and-other-history-with-codelens.md)  
[Správa konfigurace serveru s TFSConfig](http://msdn.microsoft.com/en-us/94424190-3b6b-4f33-a6b6-5807f4225b62)  
[Nástroje příkazového řádku pro TFS](http://msdn.microsoft.com/en-us/be8c997a-b97b-4e59-97f5-04db0a601a6c)