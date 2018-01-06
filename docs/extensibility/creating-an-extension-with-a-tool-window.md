---
title: "Vytváření rozšíření s okno nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e4e01959df5da96018aa8f1d06fce1076e732096
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-extension-with-a-tool-window"></a>Vytváření rozšíření s okno nástroje
V tomto postupu, další informace o použití šablona projektu VSIX a **okno nástroje vlastní** šablony položky k vytvoření rozšíření s okno nástroje.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Vytváření okno nástroje  
  
1.  Vytvoření projektu VSIX s názvem **FirstWindow**. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Po otevření projektu přidat šablonu nástroj okno Položka s názvem **MyWindow**. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **okno nástroje vlastní**. V **název** pole v dolní části okna, změňte název souboru okno nástroj na **MyWindow.cs**.  
  
3.  Sestavte projekt a spusťte ladění.  
  
     Zobrazí se experimentální instanci sady Visual Studio. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
4.  V experimentální instance, přejděte do **zobrazení nebo ostatní okna**.  
  
     Měli byste vidět položku nabídky pro **MyWindow**. Klikněte na něj.  
  
     Měli byste vidět okno nástroje s názvem **MyWindow** a tom, že tlačítko **klikněte na tlačítko mi!.**