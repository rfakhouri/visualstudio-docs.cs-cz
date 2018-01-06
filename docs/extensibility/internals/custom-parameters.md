---
title: "Vlastní parametry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wizards, custom parameters
- custom parameters
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 17a629c2d93bb5e91fb301d4da9dca825e5b8917
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="custom-parameters"></a>Vlastní parametry
Vlastní parametry řízení činnosti průvodce po spuštění průvodce. Soubor související .vsz poskytuje pole parametrů definovaný uživatelem, které jsou zabalené integrované vývojové prostředí (IDE) a předá průvodce jako pole řetězců při spuštění průvodce. Průvodce potom analyzuje pole řetězců a informace používá k řízení skutečné činnosti průvodce. Tímto způsobem můžete průvodce přizpůsobit funkce v závislosti na obsahu souboru.  
  
 Kontextové parametry, na druhé straně definovat stav projektu při spuštění průvodce. Další informace najdete v tématu [kontextové parametry](../../extensibility/internals/context-parameters.md).  
  
 Tady je příklad .vsz souboru, který má vlastní parametry:  
  
```  
VSWIZARD 8.0  
Wizard=VsWizard.VsWizard_Engine  
Param="WIZARD_NAME = Sample Wizard"  
Param="WIZARD_UI = FALSE"  
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"  
Param="PREPROCESS_FUNCTION = CanAddATLSupport"  
Param="PROJECT_TYPE = CSPROJ"  
```  
  
 Autor souboru .vsz přidá hodnoty parametrů. Když uživatel vybere **nový projekt** nebo **přidat novou položku** v nabídce Soubor nebo kliknutím pravým tlačítkem na projekt v **Průzkumníku**, rozhraní IDE shromažďuje tyto hodnoty do pole řetězce. Prostředí IDE pak zavolá projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> metoda s <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> příznak sady a volání projektu <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> metoda, která je zodpovědná za spuštění průvodce a vrátit výsledek.  
  
 Průvodce je zodpovědná za analýzy pole řetězců a správně funguje na řetězce. Tímto způsobem implementací vlastních parametrů můžete vytvořit jeden průvodce, který provede celou řadu funkcí. Jinými slovy jeden Průvodce může mít tři různé .vsz soubory. Každý soubor předá různé sady vlastních parametrů, které řídí chování Průvodce v různých situacích.  
  
 Další informace najdete v tématu [průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 [Kontextové parametry](../../extensibility/internals/context-parameters.md)   
 [Průvodci](../../extensibility/internals/wizards.md)   
 [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)