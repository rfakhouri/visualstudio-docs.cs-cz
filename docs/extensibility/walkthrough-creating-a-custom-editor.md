---
title: "Návod: Vytvoření vlastního editoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9e8ea75cb96b36f885a55cbf9f174394379dc05a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-editor"></a>Návod: Vytvoření vlastního editoru
Šablona projektu VSPackage můžete vytvořit jednoduché vlastní editor v jazyce C++.  Šablona projektu VSPackage nepodporuje projekty C# nebo Visual Basic. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="the-visual-studio-package-project-template"></a>Šablona projektu balíčku sady Visual Studio  
 Šablona projektu balíček Visual Studio najdete v **nový projekt** dialogové okno ve složce rozšíření C++  
  
### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Chcete-li vytvořit VSPackage pomocí šablony balíček Visual Studio  
  
1.  Vytvoření projektu se šablonou balíček Visual Studio.  
  
2.  Vyberte **vlastního editoru** možnost a klikněte na tlačítko **Další**. **Možností editoru** zobrazí se stránka.  
  
3.  Zadejte název vaší editor v **název editoru** pole. Zadejte příponu souboru, který chcete přidružit ve svém editoru **příponu souboru** pole. Jako editor je k dispozici pro soubory s touto příponou. Přípona souboru je zaregistrován pro sadu Visual Studio, ne pro Windows. Zadejte název souboru výchozí pro nové dokumenty, které jsou vytvořené pomocí ve svém editoru **výchozí název souboru** pole.  
  
4.  Klikněte na tlačítko **Dokončit** k vytvoření vašeho VSPackage ve složce, kterou jste zadali.  
  
### <a name="to-test-your-custom-editor"></a>K testování vlastního editoru  
  
1.  Na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **soubor**.  
  
2.  V **nainstalovaných šablonách** podokně **nový soubor** dialogové okno, vyberte soubor šablony a potom soubor typ právě zaregistrován.  
  
3.  Klikněte na tlačítko **otevřete** pro zobrazení a úpravy dokumentu.  
  
     Editor podporuje operace vyjímání a vkládání, vyhledání a nahrazení a otevřete a zatížení.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)