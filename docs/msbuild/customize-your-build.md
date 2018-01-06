---
title: "Přizpůsobení buildu | Microsoft Docs"
ms.custom: 
ms.date: 06/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 78773b3a87aff91fae92ec64365ef55620e58d44
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="customize-your-build"></a>Přizpůsobení buildu
Ve verzích nástroje MSBuild starší než verze 15 Pokud chcete zadat novou, vlastní vlastnost, která má projekty v řešení, museli jste ručně přidejte odkaz na tuto vlastnost pro každý soubor projektu v řešení. Nebo, jste museli definovat vlastnost v souboru props a explicitně importovat soubor PROPS v všechny projekty v řešení, mimo jiné.

Ale nyní můžete přidat novou vlastnost na všechny projekty v jednom kroku definováním v jediný soubor s názvem Directory.Build.props v kořenovém adresáři vašeho úložiště. Při spuštění nástroje MSBuild Microsoft.Common.props vyhledá adresářové struktury souboru Directory.Build.props (a Microsoft.Common.targets hledá Directory.Build.targets). V případě, že některou najde, naimportuje vlastnost. Directory.Build.props je soubor definovaný uživatelem, který poskytuje přizpůsobení projektů adresáře.

## <a name="directorybuildprops-example"></a>Příklad Directory.Build.props
Například, pokud chcete povolit všechny projekty pro přístup k nové Roslyn **/ deterministickou** funkce (v cílové Roslyn CoreCompile vystavené vlastnost `$(Deterministic)`), můžete to udělat následující.

1. Vytvořte nový soubor v kořenovém vašeho úložiště volána Directory.Build.props.
2. Přidejte následující kód XML do souboru.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. Spuštění nástroje MSBuild. Importuje existující vašeho projektu Microsoft.Common.props a Microsoft.Common.targets najít soubor a importujte ho.

## <a name="search-scope"></a>Obor vyhledávání
Při hledání soubor Directory.Build.props, provede MSBuild strukturu adresáře směrem nahoru z umístění vašeho projektu ($(MSBuildProjectFullPath)), zastavování po je možné vyhledat soubor Directory.Build.props. Například pokud vaše $(MSBuildProjectFullPath) c:\users\username\code\test\case1, MSBuild by spustit hledání existuje a pak hledání strukturu adresáře směrem nahoru, dokud se nachází soubor Directory.Build.props jako následující adresářovou strukturu .

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
Umístění souboru řešení není závislé na Directory.Build.props.

## <a name="import-order"></a>Import pořadí

Directory.Build.props se naimportují velmi brzy v Microsoft.Common.props, takže vlastnosti definované později nejsou k dispozici na ni. Ano Vyhněte se odkazující na vlastnosti, které ještě nejsou definovány (a tedy vyhodnotí jako prázdný).

Directory.Build.targets se naimportují z Microsoft.Common.targets po importu soubory .targets z balíčků NuGet. Ano může sloužit k přepsání vlastnosti a definované ve většině logiky sestavení cílů, ale v některých případech může být nutné udělat úpravy v souboru projektu po posledním importu.

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

Může být žádoucí, aby společných vlastností pro všechny projekty `(1)`, společných vlastností pro `src` projekty `(2-src)`a společných vlastností pro `test` projekty `(2-test)`.

Pro msbuild správně sloučit "vnitřní" soubory (`2-src` a `2-test`) "vnější" souborem (`1`), je třeba vzít v úvahu to jednou msbuild najde `Directory.Build.props` souboru, zastaví další kontrolu. Pokud chcete pokračovat, kontrolu a sloučení do vnějšího souboru, umístěte do obou vnitřní soubory toto:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

Souhrn msbuild je obecný přístup je následující:

- Pro daný projekt, msbuild vyhledá první `Directory.Build.props` směrem nahoru ve struktuře řešení sloučí s výchozím nastavením a zastaví kontrolu Další informace
- Pokud chcete, aby více úrovní najít a pak sloučit [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (viz výše) "vnější" soubor ze souboru "vnitřní"
- Pokud soubor "vnější" nemá sám také importovat něco nad ním, pak kontrolu zastaví existuje
- Chcete-li řídit proces kontrolu sloučení, použijte `$(DirectoryBuildPropsPath)` a`$(ImportDirectoryBuildProps)`

Nebo jednodušeji: první `Directory.Build.props` který neimportuje nic, je, kde msbuild zastaví.

## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
