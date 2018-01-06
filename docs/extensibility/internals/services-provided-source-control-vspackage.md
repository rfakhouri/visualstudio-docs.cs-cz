---
title: "Služby poskytované (Zdroj ovládacího prvku VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6951881e915b44c0cb0c85685280f2b770647f3a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="services-provided-source-control-vspackage"></a>Služby poskytované (Zdroj ovládacího prvku VSPackage)
Služby jsou primární mechanismus, pomocí kterého je funkce sdílené mezi VSPackages a mezi integrované vývojové prostředí (IDE) sady Visual Studio a jeho nainstalované VSPackages. Podrobný popis služeb a jejich důležitosti v integrovaném vývojovém prostředí sady Visual Studio naleznete v tématu[pomocí a poskytování služeb](../../extensibility/using-and-providing-services.md).  
  
## <a name="the-source-control-service"></a>Službu Řízení zdroje  
 Visual Studio poskytuje dvě vrstvy služeb, IDE úroveň služby a služby na úrovni balíčku. Visual Studio IDE nativně poskytuje služby na úrovni IDE. Zdrojový balíček ovládací prvek využívá některé z těchto služeb. Zdrojový balíček ovládací prvek jako VSPackage sdílí jeho funkce správy zdrojového tím, že poskytuje službu privátní zdroj ovládacího prvku vlastní. Zdrojový balíček řízení zapouzdří sadu zdroje související ovládací prvek rozhraní implementované ji ve formě kontrakt, který je použít v prostředí Visual Studio IDE.  
  
## <a name="see-also"></a>Viz také  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)