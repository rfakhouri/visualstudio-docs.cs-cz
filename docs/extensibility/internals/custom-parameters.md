---
title: Vlastní parametry | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- wizards, custom parameters
- custom parameters
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a879c7a842bdabff396fa2df31d0aa7326b19c50
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66312215"
---
# <a name="custom-parameters"></a>Vlastní parametry
Vlastní parametry řídí provoz průvodce po spuštění průvodce. Se souvisejícím *.vsz* souboru poskytují celou řadu uživatelem definované parametry, které jsou zabaleny pomocí integrovaného vývojového prostředí (IDE) a předána průvodci jako pole řetězců, které při spuštění průvodce. Průvodce potom analyzuje pole řetězců a informace používá k řízení skutečné činnosti průvodce. Tímto způsobem můžete průvodce přizpůsobit funkce v závislosti na obsah *.vsz* souboru.

 Kontextové parametry, na druhé straně definovat stav projektu při spuštění průvodce. Další informace najdete v tématu [kontextových parametrů](../../extensibility/internals/context-parameters.md).

 Tady je příklad *.vsz* soubor, který má vlastní parametry:

```
VSWIZARD 8.0
Wizard=VsWizard.VsWizard_Engine
Param="WIZARD_NAME = Sample Wizard"
Param="WIZARD_UI = FALSE"
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"
Param="PREPROCESS_FUNCTION = CanAddATLSupport"
Param="PROJECT_TYPE = CSPROJ"
```

 Autor *.vsz* soubor, přidá hodnoty parametrů. Když uživatel vybere **nový projekt** nebo **přidat novou položku** na **souboru** nabídek nebo kliknutím pravým tlačítkem myši projekt v **Průzkumníku řešení**, rozhraní IDE shromažďuje tyto hodnoty do pole řetězců. Rozhraní IDE, zavolá projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> metodu <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> příznak sady a volání projektu <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> metodu, která je zodpovědná za spuštění průvodce a vrátit výsledek.

 Průvodce je zodpovědné za parsování pole řetězců a správně funguje na řetězce. Tímto způsobem díky implementaci vlastních parametrů můžete vytvořit jeden průvodce, který provádí řadu funkcí. Jinými slovy, jeden Průvodce může mít tři různé *.vsz* soubory. Každý soubor předá jinou sadu vlastních parametrů pro řízení chování Průvodce v různých situacích.

 Další informace najdete v tématu [soubor průvodce (.vsz)](../../extensibility/internals/wizard-dot-vsz-file.md).

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>
- [Kontextové parametry](../../extensibility/internals/context-parameters.md)
- [Průvodci](../../extensibility/internals/wizards.md)
- [Soubor průvodce (.vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)