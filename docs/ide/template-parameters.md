---
title: "Parametry šablony | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
ms.assetid: 1b567143-08c6-4d7a-b484-49f0671754fe
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c9a719e39506e080ce55bad45124e34d79dbbfac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="template-parameters"></a>Parametry šablony
Pomocí parametrů v šablonách lze při vytváření instance šablony nahradit hodnoty nejdůležitějších částí šablony, jako jsou názvy tříd a obory názvů. Tyto parametry jsou nahrazovány Průvodce šablonou, která běží na pozadí, když uživatel klikne **OK** v **nový projekt** nebo **přidat novou položku** dialogová okna.  
  
## <a name="declaring-and-enabling-template-parameters"></a>Deklarace a povolení parametry šablony  
 Parametry šablony jsou deklarovány ve formátu $*parametr*$. Příklad:  
  
-   $safeprojectname$  
  
-   $ $guid1  
  
-   $ $guid5  
  
#### <a name="to-enable-parameter-substitution-in-templates"></a>Povolit nahrazení parametrů v šablonách  
  
1.  V souboru .vstemplate šablony vyhledejte prvek `ProjectItem`, který odpovídá položce, pro kterou chcete povolit náhradu parametrů.  
  
2.  Nastavte `ReplaceParameters` atribut `ProjectItem` element `true`.  
  
3.  V souboru kódu pro položku projektu zahrňte odpovídající parametry. Například následující parametr určuje, že název bezpečné projektu používat pro obor názvů v souboru:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
## <a name="reserved-template-parameters"></a>Vyhrazené parametry šablon  
 Následující tabulka uvádí parametry vyhrazené šablony, které můžete používat všechny šablony.  
  
> [!NOTE]
>  Parametry šablony rozlišují velká a malá písmena.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`clrversion`|Aktuální verze common language runtime (CLR).|  
|`GUID [1-10]`|Identifikátor GUID, používá k nahrazení identifikátoru GUID projektu v souboru projektu. Můžete zadat až 10 jedinečné identifikátory GUID (například `guid1)`.|  
|`itemname`|Název zadaný uživatelem v **přidat novou položku** dialogové okno.|  
|`machinename`|Aktuální název počítače (například Computer01).|  
|`projectname`|Název zadaný uživatelem v **nový projekt** dialogové okno.|  
|`registeredorganization`|Hodnota klíče registru z HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|  
|`rootnamespace`|Kořenový obor názvů aktuálního projektu. Tento parametr platí pouze pro šablony položek.|  
|`safeitemname`|Název zadaný uživatelem v **přidat novou položku** dialogové okno, se všemi nebezpečné znaky a odebrány mezery.|  
|`safeprojectname`|Název zadaný uživatelem v **nový projekt** dialogové okno, se všemi nebezpečné znaky a odebrány mezery.|  
|`time`|Aktuální čas ve formátu DD/MM/RRRR 00:00:00.|  
|`SpecificSolutionName`|Název řešení. Pokud je zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` obsahuje název řešení. Pokud není zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` je prázdné.|  
|`userdomain`|Aktuální uživatel domény.|  
|`username`|Aktuální uživatelské jméno.|  
|`webnamespace`|Název aktuální webové stránky. Tento parametr se používá v šabloně webové formuláře zaručit jedinečné názvy tříd. Pokud webová stránka je v kořenovém adresáři webového serveru, tento parametr šablony přeloží na kořenový adresář webového serveru.|  
|`year`|Ve formátu RRRR do aktuálního roku.|  
  
## <a name="custom-template-parameters"></a>Parametry vlastní šablony  
 Můžete zadat vlastní parametry šablony a hodnoty, kromě vyhrazené výchozí parametry šablony, které se používají při nahrazení parametru. Další informace najdete v tématu [CustomParameters – Element (šablony sady Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md)  
  
## <a name="example-replacing-files-names"></a>Příklad: Nahrazení názvů souborů  
 Můžete zadat různé názvy souborů pro položky projektu pomocí parametru s `TargetFileName` atribut. Například může určit, že soubor .exe používat jako název projektu určeného `$projectname$`, jako je název souboru.  
  
```  
<TemplateContent>  
    <ProjectItem  
        ReplaceParameters="true"  
        TargetFileName="$projectname$.exe">  
            File1.exe  
    </ProjectItem>  
      ...  
</TemplateContent>  
```  
  
## <a name="example-using-the-project-name-for-the-namespace-name"></a>Příklad: Použití názvu projektu jako název oboru názvů  
 Chcete-li použít název projektu pro obor názvů v jazyce Visual C# – třída souboru Class1.cs, použijte následující syntaxi:  
  
```  
#region Using directives  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
#endregion  
  
namespace $safeprojectname$  
{  
    public class Class1  
        {  
            public Class1()  
                {  
  
                }  
         }  
}  
```  
  
 V souboru .vstemplate šablony projektu patří následující kód XML, když odkazujete na soubor Class1.cs:  
  
```  
<TemplateContent>  
    <ProjectItem ReplaceParameters="true">  
        Class1.cs  
    </ProjectItem>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)