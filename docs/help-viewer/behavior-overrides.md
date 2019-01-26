---
title: Přepíše Help Content Manager
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b73feb967e340f66eb243013add0b650916c956
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961423"
---
# <a name="help-content-manager-overrides"></a>Přepíše Help Content Manager

Můžete změnit výchozí chování aplikace Help Viewer a funkcí souvisejících s nápovědou v integrovaném vývojovém prostředí sady Visual Studio. Některé možnosti jsou určena pomocí vytváření [.pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) souboru nastavit různé hodnoty klíče registru. Ostatní jsou nastavena přímo v registru.

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>Jak řídit chování aplikace Help Viewer pomocí souboru .pkgdef

1. Vytvoření *.pkgdef* soubor s první řádek jako `[$RootKey$\Help]`.

2. Přidat některé nebo všechny hodnoty klíče registru popsané v následující tabulce na samostatné řádky, například `"UseOnlineHelp"=dword:00000001`.

3. Zkopírujte soubor do *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\< edition\>\Common7\IDE\CommonExtensions*.

4. Spustit `devenv /updateconfiguration` v příkazovém řádku pro vývojáře.

### <a name="registry-key-values"></a>Hodnoty klíče registru

|Hodnota klíče registru|Typ|Data|Popis|
|------------------|----|----|-----------|
|NewContentAndUpdateService|odkazy řetězců|\<Adresa URL protokolu HTTP pro koncový bod služby\>|Definování koncového bodu služby jedinečný|
|UseOnlineHelp|dword|`0` Chcete-li určit místní nápovědy `1` k určení online nápovědy|Definovat výchozí nápovědy online nebo offline|
|OnlineBaseUrl|odkazy řetězců|\<Adresa URL protokolu HTTP pro koncový bod služby\>|Definovat koncový bod jedinečný F1|
|OnlineHelpPreferenceDisabled|dword|`0` Chcete-li povolit nebo `1` zakázat možnost předvoleb online nápovědy|Zakázat možnost předvoleb online nápovědy|
|DisableManageContent|dword|`0` Chcete-li povolit nebo `1` zakázat **spravovat obsah** kartě v aplikaci Help Viewer|Zakažte **spravovat obsah** kartu|
|DisableFirstRunHelpSelection|dword|`0` Chcete-li povolit nebo `1` zakázat funkce nápovědy, které jsou konfigurovány při prvním spuštění sady Visual Studio|Zakázat instalaci obsahu při prvním spuštění sady Visual Studio|

### <a name="example-pkgdef-file-contents"></a>Příklad obsahu souboru .pkgdef

```pkgdef
[$RootKey$\Help]
"NewContentAndUpdateService"="https://some.service.endpoint"
"UseOnlineHelp"=dword:00000001
"OnlineBaseUrl"="https://some.service.endpoint"
"OnlineHelpPreferenceDisabled"=dword:00000000
"DisableManageContent"=dword:00000000
"DisableFirstRunHelpSelection"=dword:00000001
```

## <a name="use-registry-editor-to-change-help-viewer-behavior"></a>Chcete-li změnit chování aplikace Help Viewer pomocí Editoru registru

Následující dva chování můžete řídit pomocí nastavení hodnoty klíčů registru v editoru registru.

|Úloha|Klíč registru|Hodnota|Data|
|----------|-----|------|----|
|Přepsat Priorita úlohy BITS|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node (na 64-bit machine)\Microsoft\Help\v2.3|BITSPriority|**popředí**, **vysokou**, **normální**, nebo **nízké**|
|Přejděte na místní úložiště obsahu v síťové sdílené složce|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\ v2.3\Catalogs\VisualStudio15|LocationPath|"*ContentStoreNetworkShare*"|

## <a name="see-also"></a>Viz také:

- [Příručka pro správce Prohlížeč nápovědy](../help-viewer/administrator-guide.md)
- [Argumenty příkazového řádku pro Help Content Manager](../help-viewer/command-line-arguments.md)
- [Microsoft Help Viewer 2.2](../help-viewer/overview.md)