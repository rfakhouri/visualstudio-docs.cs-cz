---
title: 'Postupy: ignorování chyb v úlohách | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
author: kempb
ms.author: kempb
manager: douge
ms.openlocfilehash: 5013bec8da1cfd8e74fc6ae74724fea7a8eec636
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-ignore-errors-in-tasks"></a>Postupy: Ignorování chyb v úlohách
Někdy budete chtít sestavení jako toleranci vůči chyb v určitých úloh. Pokud tyto méně závažné úlohy selže, budete chtít sestavení pokračovat, protože jej může stále vytvořit požadované výstup. Například, pokud se používá na projekt `SendMail` úloha pro odeslání e-mailové zprávy, jakmile je vytvořen jednotlivé komponenty, můžete zvážit je přijatelné pro sestavení pokračovat do dokončení, i když poštovní servery nejsou k dispozici a nelze odeslat stavové zprávy. Nebo, například pokud zprostředkující soubory jsou obvykle odstraněny během sestavení, můžete zvážit je přijatelné pro sestavení pokračovat do dokončení, i když tyto soubory nelze odstranit.  
  
## <a name="using-the-continueonerror-attribute"></a>Pomocí ContinueOnError – atribut  
 `ContinueOnError` Atribut `Task` element určuje, zda sestavení zastaví, nebo bude pokračovat, když dojde k selhání úloh. Tento atribut také určuje, zda chyby jsou považovány za chyby nebo upozornění, když dál sestavení.  
  
 `ContinueOnError` Atribut může obsahovat jednu z následujících hodnot:  
  
-   **WarnAndContinue** nebo **true**. Pokud úloha selže, úlohy v [cíl](../msbuild/target-element-msbuild.md) elementu a sestavení dále provést, a všechny chyby z úlohy se považují za upozornění.  
  
-   **ErrorAndContinue**. Pokud úloha selže, úlohy v `Target` elementu a sestavení dále provést, a všechny chyby z úlohy se považují za chyby.  
  
-   **ErrorAndStop** nebo **false** (výchozí). Pokud úloha selže, ve zbývajících úkolech v `Target` elementu a sestavení nebudou provedeny a celý `Target` elementu a sestavení považován za neúspěšný.  
  
 Verze rozhraní .NET Framework před 4.5 podporovaná jenom `true` a `false` hodnoty.  
  
 Výchozí hodnota `ContinueOnError` je `ErrorAndStop`. Pokud nastavíte atribut na `ErrorAndStop`, provedete chování explicitní každý, kdo přečte soubor projektu.  
  
#### <a name="to-ignore-an-error-in-a-task"></a>Ignorovat chybu v úloze  
  
-   Použití `ContinueOnError` atribut úlohy. Příklad:  
  
     `<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>`  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, že `Build` cíl stále běží a sestavení je považovat za úspěšné, i když `Delete` úloh selže.  
  
```xml  
<Project DefaultTargets="FakeBuild"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Files Include="*.obj"/>  
    </ItemGroup>  
    <Target Name="Clean">  
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>  
    </Target>  
  
    <Target Name="FakeBuild" DependsOnTargets="Clean">  
        <Message Text="Building after cleaning..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také
[MSBuild](../msbuild/msbuild.md)  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)