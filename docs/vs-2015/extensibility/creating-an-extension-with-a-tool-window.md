---
title: Vytváření rozšíření pomocí panelu nástrojů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: afa24a7faceade36cf6b3d19c7e86fb8d6676ba8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629481"
---
# <a name="creating-an-extension-with-a-tool-window"></a>Vytváření rozšíření pomocí panelu nástrojů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vytváření rozšíření pomocí panelu nástrojů](https://docs.microsoft.com/visualstudio/extensibility/creating-an-extension-with-a-tool-window).  
  
V tomto postupu se dozvíte, jak použít šablonu projektu VSIX a **vlastního panelu nástrojů** šablony položky k vytvoření rozšíření pomocí panelu nástrojů.  
  
## <a name="prerequisites"></a>Požadavky  
 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Vytvoření okna nástroje  
  
1.  Vytvořte projekt VSIX s názvem **FirstWindow**. Můžete najít šablonu projektu VSIX v **nový projekt** dialogového okna v části **Visual C# / rozšíření**.  
  
2.  Po otevření projektu přidat šablonu položky okna nástroje s názvem **FirstWindow**. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **Add / nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# / rozšíření** a vyberte **vlastního panelu nástrojů**. V **název** pole v dolní části okna, změňte název souboru okna nástroje, aby **FirstWindow.cs**.  
  
3.  Sestavte projekt a spusťte ladění.  
  
     Experimentální instanci sady Visual Studio se zobrazí. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
4.  V experimentální instanci aplikace, přejděte na **zobrazení / ostatní Windows**.  
  
     Měli byste vidět položku nabídky pro **FirstWindow**. Klikněte na něj.  
  
     Měli byste vidět okno nástroje s názvem **FirstWindow** a slavným výrokem tlačítko **klikněte na mě!.**

