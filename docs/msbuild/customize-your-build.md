---
title: Přizpůsobení buildu | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed8497c937006d53bf6cd6f8f5b1a773fdf44137
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="customize-your-build"></a>Přizpůsobení buildu
Ve verzích nástroje MSBuild starší než verze 15 Pokud chcete zadat novou, vlastní vlastnost, která má projekty v řešení, museli jste ručně přidejte odkaz na tuto vlastnost pro každý soubor projektu v řešení. Nebo, jste měli k definování vlastností v *props* souboru a pak můžete importovat explicitně *props* souboru v všechny projekty v řešení, mimo jiné.

Ale nyní můžete přidat novou vlastnost na všechny projekty v jednom kroku definováním v jednoho souboru s názvem *Directory.Build.props* v kořenovém adresáři vašeho úložiště. Při spuštění nástroje MSBuild *Microsoft.Common.props* vyhledá struktury adresářů pro *Directory.Build.props* souboru (a *Microsoft.Common.targets* hledá *Directory.Build.targets*). V případě, že některou najde, naimportuje vlastnost. *Directory.Build.props* je soubor definovaný uživatelem, který poskytuje přizpůsobení projektů adresáře.

## <a name="directorybuildprops-example"></a>Příklad Directory.Build.props
Například, pokud chcete povolit všechny projekty pro přístup k nové Roslyn **/ deterministickou** funkce (což je zpřístupněná Roslyn `CoreCompile` cíl vlastností `$(Deterministic)`), můžete to udělat následující.

1. Vytvořte nový soubor v kořenovém vašeho úložiště volána *Directory.Build.props*.
2. Přidejte následující kód XML do souboru.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. Spuštění nástroje MSBuild. Importuje existující vašeho projektu z *Microsoft.Common.props* a *Microsoft.Common.targets* najít soubor a importujte ho.

## <a name="search-scope"></a>Obor vyhledávání
Při hledání *Directory.Build.props* adresářové struktury souboru MSBuild směrem nahoru provede z umístění vašeho projektu (`$(MSBuildProjectFullPath)`), zastavování po je možné vyhledat *Directory.Build.props* soubor. Například pokud vaše `$(MSBuildProjectFullPath)` byla *c:\users\username\code\test\case1*MSBuild by spusťte hledání existuje a pak hledání strukturu adresáře směrem nahoru, dokud se nachází *Directory.Build.props* souboru, jako následující adresářovou strukturu.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
Umístění souboru řešení není závislé na *Directory.Build.props*.

## <a name="import-order"></a>Import pořadí

*Directory.Build.props* je velmi brzy v naimportována *Microsoft.Common.props*, takže vlastnosti definované později nejsou k dispozici na ni. Ano Vyhněte se odkazující na vlastnosti, které ještě nejsou definovány (a tedy vyhodnotí jako prázdný).

*Directory.Build.targets* je naimportovaná ze *Microsoft.Common.targets* po importu *.targets* soubory z balíčků NuGet. Ano může sloužit k přepsání vlastnosti a definované ve většině logiky sestavení cílů, ale v některých případech může být nutné udělat úpravy v souboru projektu po posledním importu.

## <a name="use-case-multi-level-merging"></a>Případ použití: víceúrovňovou sloučení

Předpokládejme, že máte tato struktura standardní řešení:

````
\
  MySolution.sln
  Directory.Build.props     (1)
  \src
    Directory.Build.props   (2-src)
    \Project1
    \Project2
  \test
    Directory.Build.props   (2-test)
    \Project1Tests
    \Project2Tests
````

Může být žádoucí, aby společných vlastností pro všechny projekty *(1)*, společných vlastností pro *src* projekty *(2-src)*a společných vlastností pro  *testování* projekty *(2-test)*.

Pro MSBuild správně sloučit "vnitřní" soubory (*2 src* a *2-test*) "vnější" souborem (*1*), je třeba vzít v úvahu, že jednou MSBuild vyhledá *Directory.Build.props* souboru, zastaví další kontrolu. Pokud chcete pokračovat, kontrolu a sloučení do vnějšího souboru, umístěte do obou vnitřní soubory toto:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

Souhrn MSBuild je obecný přístup je následující:

- Pro daný projekt, MSBuild vyhledá první *Directory.Build.props* směrem nahoru ve struktuře řešení sloučí s výchozím nastavením a zastaví kontrolu Další informace
- Pokud chcete, aby více úrovní najít a pak sloučit [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (viz výše) "vnější" soubor ze souboru "vnitřní"
- Pokud soubor "vnější" nemá sám také importovat něco nad ním, pak kontrolu zastaví existuje
- Chcete-li řídit proces kontrolu sloučení, použijte `$(DirectoryBuildPropsPath)` a `$(ImportDirectoryBuildProps)`

Nebo jednodušeji: první *Directory.Build.props* který neimportuje nic, je, kde MSBuild zastaví.

## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
