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
ms.openlocfilehash: c30c374756578fd71dd344393b58f38cacadeb19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="services-provided-source-control-vspackage"></a>Služby poskytované (Zdroj ovládacího prvku VSPackage)
Služby jsou primární mechanismus, pomocí kterého je funkce sdílené mezi VSPackages a mezi integrované vývojové prostředí (IDE) sady Visual Studio a jeho nainstalované VSPackages. Podrobný popis služeb a jejich důležitosti v integrovaném vývojovém prostředí sady Visual Studio naleznete v tématu[pomocí a poskytování služeb](../../extensibility/using-and-providing-services.md).  
  
## <a name="the-source-control-service"></a>Službu Řízení zdroje  
 Visual Studio poskytuje dvě vrstvy služeb, IDE úroveň služby a služby na úrovni balíčku. Visual Studio IDE nativně poskytuje služby na úrovni IDE. Zdrojový balíček ovládací prvek využívá některé z těchto služeb. Zdrojový balíček ovládací prvek jako VSPackage sdílí jeho funkce správy zdrojového tím, že poskytuje službu privátní zdroj ovládacího prvku vlastní. Zdrojový balíček řízení zapouzdří sadu zdroje související ovládací prvek rozhraní implementované ji ve formě kontrakt, který je použít v prostředí Visual Studio IDE.  
  
## <a name="see-also"></a>Viz také  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)