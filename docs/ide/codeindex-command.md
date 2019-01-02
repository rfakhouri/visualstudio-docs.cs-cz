---
title: Codeindex – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- command-line tools [Team Foundation Server]
- TFSConfig
- CodeIndex command [Team Foundation Server]
ms.assetid: b79568d4-6a64-4ca9-a1ee-3e57f92a9c5c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03a7f56f7b295cbfaf8eda437d6071e83b79ca44
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53898252"
---
# <a name="codeindex-command"></a>Codeindex – příkaz

Použití **CodeIndex** příkaz pro správu indexování kódu na Team Foundation Server. Můžete například chtít resetovat index pro opravu informace CodeLens nebo vypnout indexování kódu a zjistit problémy s výkonem serveru.

## <a name="required-permissions"></a>Požadovaná oprávnění

Použít **CodeIndex** příkaz, musíte být členem skupiny **správci serveru Team Foundation** skupiny zabezpečení. Zobrazit [oprávnění a skupiny definované pro služby Azure DevOps a TFS](/azure/devops/organizations/security/permissions?view=vsts).

> [!NOTE]
> I když se přihlásíte s přihlašovacími údaji správce, musíte otevřít okno příkazového řádku se zvýšenými oprávněními ke spuštění tohoto příkazu. Tento příkaz musíte také spustit z aplikační vrstvy pro Team Foundation.

## <a name="syntax"></a>Syntaxe

```cmd
TFSConfig CodeIndex /indexingStatus | /setIndexing:[ on | off | keepupOnly ] | /ignoreList:[ add | remove | removeAll | view ] ServerPath | /listLargeFiles [/fileCount:FileCount] [/minSize:MinSize] | /reindexAll | /destroyCodeIndex [/noPrompt] | /temporaryDataSizeLimit:[ view | <SizeInGBs> | disable ] | /indexHistoryPeriod:[ view | all | <NumberOfMonths> ] [/collectionName:CollectionName | /collectionId:CollectionId]
```

### <a name="parameters"></a>Parametry

|**Argument**|**Popis**|
|------------------| - |
|`CollectionName`|Určuje název kolekce projektů. Pokud název obsahuje mezery, uzavřete ho uvozovek, například "Fabrikam web".|
|`CollectionId`|Určuje identifikační číslo kolekce projektu.|
|`ServerPath`|Určuje cestu k souboru kódu.|

|**Možnost**|**Popis**|
|----------------| - |
|**/indexingStatus**|Zobrazení stavu a konfigurace služby indexování kódu.|
|**/setIndexing:**[na &#124; vypnout &#124; keepupOnly]|-   **na**: Zahájení indexování všech sad změn.<br />-   **vypnout**: Ukončení indexování všech sad změn.<br />-   **keepupOnly**: Zastavení indexování dříve vytvořených sad změn a spuštění indexování pouze nových sad změn.|
|**/ignoreList:**[Přidat &#124; odebrat &#124; removeAll &#124; zobrazení] `ServerPath`<br /><br /> Na začátku, konci nebo na obou koncích cesty k serveru můžete použít zástupný znak (*).|Určuje seznam souborů s kódem a jejich cesty, které nechcete indexované.<br /><br /> -   **Přidat**: Přidejte soubor, který nechcete indexovaných do seznamu ignorovaných souborů.<br />-   **Odebrat**: Odstranění souboru, který chcete indexovat ze seznamu ignorovaných souborů.<br />-   **removeAll**: Vymazání seznamu ignorovaných souborů a zahájení indexování všech souborů.<br />-   **zobrazení**: Zobrazit všechny soubory, které nejsou indexovat.|
|**/listLargeFiles [/ fileCount:** `FileCount` **/minSize:** `MinSize`]|Zobrazí zadaný počet souborů, která překračuje zadanou velikost v KB. Pak můžete použít **/ignoreList** možnost, chcete-li z indexování vyloučit tyto soubory.|
|**/reindexAll**|Vymažte dříve indexovaná data a spusťte indexování znovu.|
|**/destroyCodeIndex [/ noprompt]**|Smazat index kódu a odstranit všechna indexovaná data. Pokud používáte nevyžaduje potvrzení **/noprompt** možnost.|
|**/temporaryDataSizeLimit**: [zobrazení &#124; <`SizeInGBs`> &#124; zakázat]|Určit, kolik dočasná data, která vytvoří CodeLens při zpracování sady změn. Výchozí omezení je 2 GB.<br /><br /> -   **zobrazení**: Zobrazit aktuální limit velikosti.<br />-   `SizeInGBs`: Změňte limit velikosti.<br />-   **Zakázat**: Odeberte omezení velikosti.<br /><br /> Toto omezení je zaškrtnuto, než funkce CodeLens zpracuje novou sadu změn. Dočasná data, která překračuje tento limit, CodeLens pozastaví zpracování poslední sady změn, nikoli nové značky. CodeLens se restartuje po data se vyčistí a klesne pod tento limit zpracování. Čištění se spustí automaticky jednou denně. To znamená, že dočasná data, která může překročit tento limit, dokud se čištění se spustí.|
|**/indexHistoryPeriod**: [zobrazení &#124; všechny &#124; <`NumberOfMonths`>]|Ovládací prvek, jak dlouho se má indexovat historii změn. To má vliv na tom, kolik historie CodeLens ukazuje. Výchozí limit je 12 měsíců. To znamená, že funkce CodeLens ukazuje historii změn z pouze za posledních 12 měsíců.<br /><br /> -   **zobrazení**: Zobrazte aktuální počet měsíců.<br />-   **všechny**: Index všech historii změn.<br />-   `NumberOfMonths`: Změňte počet měsíců pro index historii změn.|
|**/collectionName:** `CollectionName`|Určuje název kolekce projektu, ve kterém se má spustit **CodeIndex** příkazu. Povinné, pokud nepoužíváte **/CollectionId**.|
|**/collectionId:** `CollectionId`|Určuje identifikační číslo kolekce projektu, ve kterém se spustí **CodeIndex** příkazu. Povinné, pokud nepoužíváte **/CollectionName**.|

## <a name="examples"></a>Příklady

> [!NOTE]
> Vzorové společnosti, organizace, produkty, názvy domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené.  Žádné jejich spojení se skutečnou společností, organizaci, produktu, název domény, e-mailovou adresu, loga, osoby, místa nebo události je určena ji vyvozovat.

 Chcete-li zobrazit kód stavu a konfiguraci indexování:

```cmd
TFSConfig CodeIndex /indexingStatus /collectionName:"Fabrikam Website"
```

 Zahájení indexování všech sad změn:

```cmd
TFSConfig CodeIndex /setIndexing:on /collectionName:"Fabrikam Website"
```

 Chcete-li zastavit indexování dříve vytvořených sad změn a spustit indexování pouze nových sad změn:

```cmd
TFSConfig CodeIndex /setIndexing:keepupOnly /collectionName:"Fabrikam Website"
```

 K vyhledání až 50 souborů, které jsou větší než 10 KB:

```cmd
TFSConfig CodeIndex /listLargeFiles /fileCount:50 /minSize:10 /collectionName:"Fabrikam Website"
```

 Chcete-li z indexování vyloučit určitý soubor a přidejte do seznamu ignorovaných souborů:

```cmd
TFSConfig CodeIndex /ignoreList:add "$/Fabrikam Website/Catalog.cs" /collectionName:"Fabrikam Website"
```

 Pokud chcete zobrazit všechny soubory, které nejsou indexována:

```cmd
TFSConfig CodeIndex /ignoreList:view
```

 Vymažte dříve indexovaná data a znovu spustit indexování:

```cmd
TFSConfig CodeIndex /reindexAll /collectionName:"Fabrikam Website"
```

 Uložte veškerá historie změn:

```cmd
TFSConfig CodeIndex /indexHistoryPeriod:all /collectionName:"Fabrikam Website"
```

 Odebrání omezení velikosti pro dočasná data CodeLens a pokračovat indexování bez ohledu na velikost dočasných dat:

```cmd
TFSConfig CodeIndex /temporaryDataSizeLimit:disable /collectionName:"Fabrikam Website"
```

 Chcete-li odstranit kód indexu s potvrzením:

```cmd
TFSConfig CodeIndex /destroyCodeIndex /collectionName:"Fabrikam Website"
```

## <a name="see-also"></a>Viz také:

- [Nalezení změn kódu a další historie pomocí CodeLensu](../ide/find-code-changes-and-other-history-with-codelens.md)
- [Správa konfigurace serveru pomocí nástroje TFSConfig](/tfs/server/ref/command-line/tfsconfig-cmd)