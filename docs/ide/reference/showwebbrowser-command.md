---
title: "Showwebbrowser – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4a54023892d1432639fd1211273195b941e8f081
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz
Zobrazí adresu URL, zadejte v okně webového prohlížeče buď v rámci integrované vývojové prostředí (IDE) nebo externí k prostředí IDE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
View.ShowWebBrowser URL [/new][/ext]  
```  
  
## <a name="arguments"></a>Arguments  
 `URL`  
 Požadováno. Adresa URL (Uniform Resource Locator) pro webovou stránku.  
  
## <a name="switches"></a>Přepínače  
 / new  
 Volitelné. Určuje, že stránka se zobrazí v nové instanci webového prohlížeče.  
  
 /ext  
 Volitelné. Určuje, zda stránky se zobrazí ve webovém prohlížeči výchozí mimo prostředí IDE.  
  
## <a name="remarks"></a>Poznámky  
 Alias pro funkci **showwebbrowser –** příkaz je **přejděte** nebo **nav**.  
  
## <a name="example"></a>Příklad  
 Následující příklad zobrazuje na webu MSDN Online domovskou stránku ve webovém prohlížeči mimo prostředí IDE. Pokud je již spuštěna instance webového prohlížeče, použije se; v opačném případě se spustí novou instanci.  
  
```  
>View.ShowWebBrowser http://msdn.microsoft.com /ext  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)