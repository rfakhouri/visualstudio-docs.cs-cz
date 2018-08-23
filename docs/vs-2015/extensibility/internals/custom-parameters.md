---
title: Vlastní parametry | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wizards, custom parameters
- custom parameters
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 21d85eb55e20eb27a67856cec1fea7f6fa539b41
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670161"
---
# <a name="custom-parameters"></a>Vlastní parametry
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vlastní parametry](https://docs.microsoft.com/visualstudio/extensibility/internals/custom-parameters).  
  
Vlastní parametry řídí provoz průvodce po spuštění průvodce. Související soubor poskytují celou řadu uživatelem definované parametry, které jsou zabaleny pomocí integrovaného vývojového prostředí (IDE) a předána průvodci jako pole řetězců, které při spuštění průvodce. Průvodce potom analyzuje pole řetězců a informace používá k řízení skutečné činnosti průvodce. Tímto způsobem můžete průvodce přizpůsobit funkce v závislosti na obsahu souboru.  
  
 Kontextové parametry, na druhé straně definovat stav projektu při spuštění průvodce. Další informace najdete v tématu [kontextových parametrů](../../extensibility/internals/context-parameters.md).  
  
 Tady je příklad souboru, který má vlastní parametry:  
  
```  
VSWIZARD 8.0  
Wizard=VsWizard.VsWizard_Engine  
Param="WIZARD_NAME = Sample Wizard"  
Param="WIZARD_UI = FALSE"  
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"  
Param="PREPROCESS_FUNCTION = CanAddATLSupport"  
Param="PROJECT_TYPE = CSPROJ"  
```  
  
 Autorem tohoto souboru .vsz přidá hodnoty parametrů. Když uživatel vybere **nový projekt** nebo **přidat novou položku** v nabídce Soubor nebo kliknutím pravým tlačítkem myši projekt v **Průzkumníka řešení**, rozhraní IDE shromažďuje tyto hodnoty do pole řetězce. Rozhraní IDE, zavolá projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> metodu <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> příznak sady a volání projektu <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> metodu, která je zodpovědná za spuštění průvodce a vrátit výsledek.  
  
 Průvodce je zodpovědné za parsování pole řetězců a správně funguje na řetězce. Tímto způsobem díky implementaci vlastních parametrů můžete vytvořit jeden průvodce, který provádí řadu funkcí. Jinými slovy jeden Průvodce může mít tři různé .vsz soubory. Každý soubor předá jinou sadu vlastních parametrů pro řízení chování Průvodce v různých situacích.  
  
 Další informace najdete v tématu [průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 [Kontextové parametry](../../extensibility/internals/context-parameters.md)   
 [Průvodce](../../extensibility/internals/wizards.md)   
 [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)

