---
title: Rozšíření diagramů vrstev | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- layer diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: 41
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: af5058ba0d88c91ea89a33523002294339dd32f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669524"
---
# <a name="extend-layer-diagrams"></a>Rozšíření diagramů vrstev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [rozšíření diagramů závislostí](https://docs.microsoft.com/visualstudio/modeling/extend-layer-diagrams).  
  
Můžete napsat kód k vytvoření a aktualizaci diagramy vrstev a k ověření struktury program kódu oproti diagramům vrstev v sadě Visual Studio. Můžete přidat příkazy, které se zobrazují v nabídce místní (objektu context) diagramů, přizpůsobení gesta přetažení myší a přístup k modelu vrstvy z textových šablon. Můžete zabalit tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuovat ostatním uživatelům aplikace Visual Studio.  
  
 Další informace o diagramech vrstev naleznete v tématu:  
  
-   [Diagramy vrstev: referenční dokumentace](../modeling/layer-diagrams-reference.md)  
  
-   [Diagramy vrstev: pokyny](../modeling/layer-diagrams-guidelines.md)  
  
-   [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="prereqs"></a> Požadavky  
 Musí být nainstalovaný na počítači, kde chcete vyvíjet rozšíření vrstvy:  
  
-   Visual Studio  
  
-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)  
  
-   [Sada Modeling SDK for Visual Studio 2015](http://www.microsoft.com/download/details.aspx?id=48148)  
  
 Musí mít vhodnou verzi sady Visual Studio nainstalované na počítači, ve kterém chcete spustit rozšíření vrstvy. Další informace najdete v tématu [nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md).  
  
 Které verze sady Visual Studio podporují diagramy vrstev najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přidávání příkazů a gest do diagramů vrstev](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [Přidání ověřování vlastní architektury do diagramů vrstev](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [Přidání vlastních vlastností do diagramů vrstev](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [Procházení a aktualizace modelů vrstev v programovém kódu](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [Nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md)  
  
 [Řešení potíží s rozšířeními pro diagramy vrstev](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>Viz také  
 [Definování a instalace rozšíření modelování](../modeling/define-and-install-a-modeling-extension.md)   
 [Diagramy vrstev: referenční dokumentace](../modeling/layer-diagrams-reference.md)   
 [Diagramy vrstev: pokyny](../modeling/layer-diagrams-guidelines.md)   
 [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)   
 [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)   
 [Generování souborů z modelu UML](../modeling/generate-files-from-a-uml-model.md)   
 [Otevření modelu UML pomocí rozhraní API sady Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md)



