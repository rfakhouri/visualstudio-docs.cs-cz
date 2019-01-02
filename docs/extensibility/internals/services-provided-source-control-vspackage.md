---
title: Služby poskytované (řízení zdrojového balíčku VSPackage) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5cbc107b1b300538cf9a94a89a77d8ac9e2ff728
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53828534"
---
# <a name="services-provided-source-control-vspackage"></a>Poskytované služby (balíček VSPackage správy zdrojového kódu)
Služby představují hlavní mechanismus, pomocí kterého je funkce sdílené mezi rozšíření VSPackages a mezi integrovaného vývojového prostředí (IDE) sady Visual Studio a jeho nainstalované rozšíření VSPackages. Podrobný popis služeb a jejich význam v integrovaném vývojovém prostředí sady Visual Studio najdete v tématu[Using a poskytování služeb](../../extensibility/using-and-providing-services.md).  
  
## <a name="the-source-control-service"></a>Službu správy zdrojových kódů  
 Visual Studio poskytuje dvě vrstvy služby, IDE úrovně služby a služby na úrovni balíčku. Integrované vývojové prostředí sady Visual Studio nativně poskytuje služby na úrovni prostředí IDE. Zdrojový balíček ovládací prvek využívá některé z těchto služeb. Zdrojový balíček ovládací prvek jako VSPackage sdílí tím, že poskytuje služby privátní zdrojového ovládacího prvku vlastní jeho funkce správy zdrojového kódu. Zdrojový ovládací prvek balíček zapouzdřuje sadu zdroje týkající se ovládací prvek rozhraní implementované ji ve formě kontrakt, který lze použít v integrovaném vývojovém prostředí sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)