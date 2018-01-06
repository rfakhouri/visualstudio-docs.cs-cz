---
title: "&lt;entrypointscollection –&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <entryPointsCollection> element
- application manifests [Office development in Visual Studio], <entryPointsCollection> element
- entryPointsCollection element
ms.assetid: da386d67-e45f-467c-a9ba-9b8451b520eb
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: de32c5de84bf915bf3e9de21171ec3ab1ad7aee7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltentrypointscollectiongt-element-office-development-in-visual-studio"></a>&lt;entrypointscollection –&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `entryPointsCollection` Element `vstav3` obor názvů obsahuje všechny `entryPoints` elementy související s řešení pro systém Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<entryPointsCollection>  
  <entryPoints>  
    <entryPoint>  
    </entryPoint>  
    <entryPoint>  
    </entryPoint>  
    <entryPoint>  
    </entryPoint>  
  </entryPoints>  
</entryPointsCollection>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `entryPointsCollection` Element je povinná a je v `vstav3` oboru názvů. Podřízené elementy musí být také v tomto oboru názvů. Existuje pouze jeden `entryPointsCollection` element definovaný v manifestu aplikace.  
  
 `entryPointsCollection` Element nemá žádné atributy.  
  
 `entryPointsCollection`obsahuje následující prvky.  
  
### <a name="entrypoints"></a>entryPoints  
 Požadováno. Role `entryPoints` element v `vstav3` obor názvů je definován v [& č. 60; entryPoints & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/entrypoints-element-office-development-in-visual-studio.md).  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `entryPointsCollection` element v manifestu aplikace nasazené pomocí řešení úrovni dokumentu [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.ThisWorkbook">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet1">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet2">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
      <vstav3:entryPoint   
        class="ContosoExcelWorkbook.Sheet3">  
        <assemblyIdentity   
          name="ContosoExcelWorkbook"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
```  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `entryPointsCollection` element v manifestu aplikace pro řešení s úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
      <vstav3:entryPoint   
        class="ContosoOutlookAddIn.ThisAddIn">  
        <assemblyIdentity   
          name="ContosoOutlookAddIn"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
```  
  
## <a name="multi-project-deployment-example"></a>Příklad nasazení vícenásobného projektu  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `entryPointsCollection` element v manifestu aplikace pro nasazení vícenásobného projektu s dvě řešení pro systém Office. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:entryPointsCollection>  
      <vstav3:entryPoints   
        id="ContosoExcel">  
        <vstav3:entryPoint   
          class="ContosoExcelWorkbook.ThisWorkbook">  
          <assemblyIdentity   
            name="ContosoExcelWorkbook"   
            version="1.0.0.0"   
            language="neutral"   
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:entryPoint   
          class="ContosoExcelWorkbook.Sheet1">  
          <assemblyIdentity   
            name="ContosoExcelWorkbook"   
            version="1.0.0.0"   
            language="neutral"   
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:entryPoint   
          class="ContosoExcelWorkbook.Sheet2">  
          <assemblyIdentity   
            name="ContosoExcelWorkbook"   
            version="1.0.0.0"   
            language="neutral"   
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:entryPoint   
          class="ContosoExcelWorkbook.Sheet3">  
          <assemblyIdentity   
            name="ContosoExcelWorkbook"   
            version="1.0.0.0"   
            language="neutral"   
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
      </vstav3:entryPoints>  
      <vstav3:entryPoints   
        id="ContosoOutlook">  
        <vstav3:entryPoint   
          class="ContosoOutlookAddIn.ThisAddIn">  
          <assemblyIdentity   
            name="ContosoOutlookAddIn"   
            version="1.0.0.0"   
            language="neutral"   
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
      </vstav3:entryPoints>  
    </vstav3:entryPointsCollection>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  