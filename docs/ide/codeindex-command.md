---
title: CodeIndex – – příkaz
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- command-line tools [Team Foundation Server]
- TFSConfig
- CodeIndex command [Team Foundation Server]
ms.assetid: b79568d4-6a64-4ca9-a1ee-3e57f92a9c5c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: edd794d647d0af63edd133a65fbaad569e067e21
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924092"
---
# <a name="codeindex-command"></a>CodeIndex – – příkaz

Pomocí příkazu **CodeIndex –** můžete spravovat indexování kódu na Team Foundation Server. Můžete například chtít obnovit index, aby opravil CodeLens informace, nebo vypnout indexování a prozkoumat problémy s výkonem serveru.

## <a name="required-permissions"></a>Požadovaná oprávnění

Chcete-li použít příkaz **CodeIndex –** , musíte být členem skupiny zabezpečení **Správci Team Foundation** . Viz [oprávnění a skupiny definované pro Azure DevOps Services a TFS](/azure/devops/organizations/security/permissions?view=vsts).

> [!NOTE]
> I v případě, že se přihlašujete pomocí pověření správce, je nutné otevřít okno příkazového řádku se zvýšenými oprávněními ke spuštění tohoto příkazu. Tento příkaz musíte spustit také z aplikační vrstvy pro Team Foundation.

## <a name="syntax"></a>Syntaxe

```cmd
TFSConfig CodeIndex /indexingStatus | /setIndexing:[ on | off | keepupOnly ] | /ignoreList:[ add | remove | removeAll | view ] ServerPath | /listLargeFiles [/fileCount:FileCount] [/minSize:MinSize] | /reindexAll | /destroyCodeIndex [/noPrompt] | /temporaryDataSizeLimit:[ view | <SizeInGBs> | disable ] | /indexHistoryPeriod:[ view | all | <NumberOfMonths> ] [/collectionName:CollectionName | /collectionId:CollectionId]
```

### <a name="parameters"></a>Parametry

|**Argument**|**Popis**|
|------------------| - |
|`CollectionName`|Určuje název kolekce projektu. Pokud název obsahuje mezery, uzavřete název do uvozovek, například "Fabrikam web".|
|`CollectionId`|Určuje identifikační číslo kolekce projektu.|
|`ServerPath`|Určuje cestu k souboru kódu.|

|**Možnost**|**Popis**|
|----------------| - |
|**/indexingStatus**|Zobrazit stav a konfiguraci služby indexování kódu.|
|**/setIndexing:** [ &#124; vypnuto &#124; keepupOnly]|-   **zapnuto**: Spustit indexování všech sad změn.<br />-   **vypnuto**: Zastavit indexování všech sad změn.<br />-   **keepupOnly**: Zastavte indexování dříve vytvořených sad změn a zahajte indexování pouze nových sad změn.|
|**/ignorelist:** [přidat &#124; odebrání &#124; zobrazení &#124; RemoveAll]`ServerPath`<br /><br /> Můžete použít zástupný znak (*) na začátku, na konci nebo na obou koncích cesty serveru.|Určuje seznam souborů kódu a jejich cesty, které nechcete indexovat.<br /><br /> -   **Přidat**: Přidejte soubor, který nechcete indexovat, do seznamu ignorovaných souborů.<br />-   **remove**: Odeberte soubor, který chcete indexovat, ze seznamu ignorovaných souborů.<br />-   **removeAll**: Vymažte seznam ignorovaných souborů a spusťte indexování všech souborů.<br />-   **Zobrazit**: Zobrazit všechny soubory, které nejsou indexovány.|
|**/listLargeFiles [/FileCount:** `FileCount` **/minSize:** `MinSize`]|Zobrazuje zadaný počet souborů, které přesahují zadanou velikost v KB. Pak můžete použít možnost **/ignorelist** k vyloučení těchto souborů z indexování.|
|**/reindexAll**|Vymažte dříve indexovaná data a znovu spusťte indexování.|
|**/destroyCodeIndex [/noPrompt]**|Odstraňte index kódu a odeberte všechna indexovaná data. Nevyžaduje potvrzení, pokud použijete možnost **/NoPrompt** .|
|**/temporaryDataSizeLimit**: [zobrazení &#124; <`SizeInGBs`> &#124; zakázat]|Určuje, kolik dočasných dat, která CodeLens vytvoří při zpracování sad změn. Výchozí limit je 2 GB.<br /><br /> -   **Zobrazit**: Zobrazí aktuální limit velikosti.<br />-   `SizeInGBs`: Změňte limit velikosti.<br />-   **Zakázat**: Odeberte limit velikosti.<br /><br /> Toto omezení je zaškrtnuto před tím, než CodeLens zpracuje novou sadu změn. Pokud dočasná data překročí tento limit, CodeLens pozastaví zpracování minulých sad změn, nikoli nových. CodeLens restartuje zpracování po vyčištění dat a klesne pod tento limit. Automatické čištění se spustí jednou denně. To znamená, že dočasná data mohou překročit tento limit, dokud nebude spuštěno čištění.|
|**/indexHistoryPeriod**: [Zobrazit &#124; všechny &#124; <`NumberOfMonths`>]|Určuje, jak dlouho se má indexovat historie změn indexovat. To má vliv na to, kolik historie CodeLens ukazuje. Výchozí limit je 12 měsíců. To znamená, že CodeLens zobrazuje historii změn jenom za posledních 12 měsíců.<br /><br /> -   **Zobrazit**: Zobrazí aktuální počet měsíců.<br />-   **vše**: Indexovat veškerou historii změn<br />-   `NumberOfMonths`: Změna počtu měsíců použitých k indexování historie změn|
|**/CollectionName:** `CollectionName`|Určuje název kolekce projektu, na které se má spustit příkaz **CodeIndex –** . Vyžaduje se, pokud nepoužíváte **/CollectionID**.|
|**/collectionId:** `CollectionId`|Určuje identifikační číslo kolekce projektu, na které se má spustit příkaz **CodeIndex –** . Vyžaduje se, pokud nepoužíváte **/CollectionName**.|

## <a name="examples"></a>Příklady

> [!NOTE]
> Ukázkové společnosti, organizace, produkty, názvy domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené.  Žádná spojitost se skutečnou společností, organizací, produktem, názvem domény, e-mailovou adresou, logem, osobou, místem a událostmi není zamýšlená nebo by se měla odvodit.

Chcete-li zobrazit stav a konfiguraci indexování kódu:

```cmd
TFSConfig CodeIndex /indexingStatus /collectionName:"Fabrikam Website"
```

Spuštění indexování všech sad změn:

```cmd
TFSConfig CodeIndex /setIndexing:on /collectionName:"Fabrikam Website"
```

Zastavení indexování dříve vytvořených sad změn a zahájení indexování pouze nových sad změn:

```cmd
TFSConfig CodeIndex /setIndexing:keepupOnly /collectionName:"Fabrikam Website"
```

Pokud chcete najít až 50 souborů, které jsou větší než 10 KB:

```cmd
TFSConfig CodeIndex /listLargeFiles /fileCount:50 /minSize:10 /collectionName:"Fabrikam Website"
```

Vyloučení konkrétního souboru z indexování a jeho přidání do seznamu ignorovaných souborů:

```cmd
TFSConfig CodeIndex /ignoreList:add "$/Fabrikam Website/Catalog.cs" /collectionName:"Fabrikam Website"
```

Chcete-li zobrazit všechny soubory, které nejsou indexovány:

```cmd
TFSConfig CodeIndex /ignoreList:view
```

Chcete-li vymazat dříve indexovaná data a znovu spustit indexování:

```cmd
TFSConfig CodeIndex /reindexAll /collectionName:"Fabrikam Website"
```

Uložení historie všech sad změn:

```cmd
TFSConfig CodeIndex /indexHistoryPeriod:all /collectionName:"Fabrikam Website"
```

Chcete-li odebrat omezení velikosti CodeLens dočasných dat a pokračovat v indexování bez ohledu na velikost dočasného data:

```cmd
TFSConfig CodeIndex /temporaryDataSizeLimit:disable /collectionName:"Fabrikam Website"
```

Postup odstranění indexu kódu s potvrzením:

```cmd
TFSConfig CodeIndex /destroyCodeIndex /collectionName:"Fabrikam Website"
```

## <a name="see-also"></a>Viz také:

- [Nalezení změn kódu a další historie pomocí CodeLensu](../ide/find-code-changes-and-other-history-with-codelens.md)
- [Správa konfigurace serveru pomocí příkazu TFSConfig](/tfs/server/ref/command-line/tfsconfig-cmd)