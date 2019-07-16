---
title: Rozšíření diagramů vrstev | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- layer diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: 41
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: af191c929b88f1bda76896061359b7315517beb5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182874"
---
# <a name="extend-layer-diagrams"></a>Rozšíření diagramů vrstev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete napsat kód k vytvoření a aktualizaci diagramy vrstev a k ověření struktury program kódu oproti diagramům vrstev v sadě Visual Studio. Můžete přidat příkazy, které se zobrazují v nabídce místní (objektu context) diagramů, přizpůsobení gesta přetažení myší a přístup k modelu vrstvy z textových šablon. Můžete zabalit tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuovat ostatním uživatelům aplikace Visual Studio.  
  
 Další informace o diagramech vrstev naleznete v tématu:  
  
- [Diagramy vrstev: Referenční dokumentace](../modeling/layer-diagrams-reference.md)  
  
- [Diagramy vrstev: Pokyny](../modeling/layer-diagrams-guidelines.md)  
  
- [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
- [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)  
  
## <a name="prereqs"></a> Požadavky  
 Musí být nainstalovaný na počítači, kde chcete vyvíjet rozšíření vrstvy:  
  
- Visual Studio  
  
- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)  
  
- [Sada Modeling SDK for Visual Studio 2015](http://www.microsoft.com/download/details.aspx?id=48148)  
  
  Musí mít vhodnou verzi sady Visual Studio nainstalované na počítači, ve kterém chcete spustit rozšíření vrstvy. Další informace najdete v tématu [nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md).  
  
  Které verze sady Visual Studio podporují diagramy vrstev najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přidávání příkazů a gest do diagramů vrstev](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [Přidání ověřování vlastní architektury do diagramů vrstev](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [Přidání vlastních vlastností do diagramů vrstev](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [Procházení a aktualizace modelů vrstev v programovém kódu](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [Nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md)  
  
 [Řešení potíží s rozšířeními pro diagramy vrstev](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>Viz také  
 [Definování a instalace rozšíření modelování](../modeling/define-and-install-a-modeling-extension.md)   
 [Diagramy vrstev: Referenční dokumentace](../modeling/layer-diagrams-reference.md)   
 [Diagramy vrstev: Pokyny](../modeling/layer-diagrams-guidelines.md)   
 [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)   
 [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)   
 [Generování souborů z modelu UML](../modeling/generate-files-from-a-uml-model.md)   
 [Otevření modelu UML pomocí rozhraní API sady Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md)
