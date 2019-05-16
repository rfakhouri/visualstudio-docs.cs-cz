---
title: Showwebbrowser – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c3cd5d04efab6f6cb5641c7e0c4c2a8547e1ef00
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65689417"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
View.ShowWebBrowser URL [/new][/ext]  
```  
  
## <a name="arguments"></a>Arguments  
 `URL`  
 Povinný parametr. Adresa URL (Uniform Resource Locator) pro webový server.  
  
## <a name="switches"></a>Přepínače  
 / Nový  
 Volitelné. Určuje, že se zobrazí v nové instanci webového prohlížeče.  
  
 /ext  
 Volitelné. Určuje, že se zobrazí ve webovém prohlížeči výchozí mimo rozhraní IDE.  
  
## <a name="remarks"></a>Poznámky  
 Alias **showwebbrowser –** příkaz je **přejděte** nebo **nav**.  
  
## <a name="example"></a>Příklad  
 Následující příklad zobrazí domovská stránka MSDN Online ve webovém prohlížeči mimo rozhraní IDE. Pokud instance webového prohlížeče je už otevřená, je použit. v opačném případě se spustí novou instanci.  
  
```  
>View.ShowWebBrowser https://msdn.microsoft.com /ext  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
