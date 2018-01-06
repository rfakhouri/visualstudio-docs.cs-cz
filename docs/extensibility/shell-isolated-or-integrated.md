---
redirect_url: shell/shell-isolated-or-integrated
title: "Prostředí shell (izolovaný nebo integrované) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell
- Visual Studio, Shell
- Shell [Visual Studio]
- Visual Studio shell, shell-based applications
- Shell [Visual Studio], shell-based applications
ms.assetid: c64a9bf0-9bf8-45c3-8fa2-306fa6cab66a
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 787fd7c6980df9809fed9582f4ec8da81de8f862
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="shell-isolated-or-integrated"></a>Prostředí shell (izolovaný nebo integrované)
Můžete vytvořit vlastní aplikace založené na sadě Visual Studio v režimu integrovaném nebo izolované. V integrovaném režimu jsou k dispozici kromě aplikace mnoho funkcí sady Visual Studio. V izolovaném režimu zvolte podmnožinu funkcí sady Visual Studio, které chcete distribuovat spolu s vlastní rozšíření.  
  
## <a name="integrated-mode"></a>Integrovaný režim  
 Integrovaný režim umožňuje uživatelům používat standardní funkce sady Visual Studio společně s vlastních nástrojů. Integrované prostředí je určena především pro hostování programovací jazyky a nástrojů pro vývoj softwaru.  
  
 Vlastní nástroje, které jsou postaveny na integrované prostředí automaticky sloučí s jiné edice sady Visual Studio, který je nainstalován na stejném počítači. Distribuovatelnou verzi prostředí sady Visual Studio integrované můžete zadat, pokud již není nainstalována sada Visual Studio.  
  
 Distribuovatelnou verzi prostředí sady Visual Studio integrované nezahrnuje programovací jazyky a funkce, které podporují jejich odpovídajících projektu systémy.  
  
> [!NOTE]
>  Integrovaný režim prostředí sady Visual Studio můžete instalovat s všechny edice sady Visual Studio kromě edice Express.  
  
 Další informace najdete v tématu [prostředí sady Visual Studio (integrovaný režim)](../extensibility/visual-studio-shell-integrated.md).  
  
## <a name="isolated-mode"></a>Izolovaný režim  
 Izolovaný režim umožňuje vytvářet vlastní nástroje, které spustit souběžně sdílená s jinými verzemi sady Visual Studio. Je určena především pro nástroje, které mají přístup ke službám Visual Studio bez v závislosti na všechny standardní funkce sady Visual Studio. Můžete přizpůsobit vzhled aplikace založené na prostředí sady Visual Studio izolované. Snadno můžete vypnout funkce a skupiny příkaz nabídky, které nechcete, aby se objeví spolu s vaší aplikace.  
  
 Další informace najdete v tématu [izolované prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md).  
  
## <a name="distributing-your-integrated-or-isolated-shell-application"></a>Distribuce aplikace integrované nebo izolované prostředí  
 Chcete-li distribuovat aplikace integrované nebo izolované prostředí, musíte zahrnout aplikace, speciální integrované nebo izolované prostředí redistributable a instalační program. Další informace o distribuci a instalace najdete v tématu [distribuci izolované prostředí aplikace](../extensibility/distributing-isolated-shell-applications.md).  
  
> [!IMPORTANT]
>  [Licenční smlouvy koncovým uživatelem (EULA)](https://www.visualstudio.com/en-us/support/legal/mt171552) pro Visual Studio integrované a izolované součásti pro obsahuje oddíl na shromažďování dat (**část 3. Data**).  Popisuje data o využití zákazníka, které může společnost Microsoft neshromažďuje od uživatelů buď integrované nebo izolované prostředí software, který sestavení do své aplikace. Další informace najdete v tématu [Microsoft Visual Studio rodiny ochrany osobních údajů produktu](https://www.visualstudio.com/en-us/dn948229).  
>   
>  Budete-li shromažďovat data o samostatný využití od zákazníků prostřednictvím vaší aplikace, je nutné zadat příslušné oznámení pro uživatele co shromáždíte vaší aplikace.  Při distribuci softwaru izolované nebo integrované prostředí v rámci vaší aplikace podle Visual Studio Software Development Kit licenci, musí obsahovat jednu z těchto možností:  
>   
>  -   Licenční smlouvu konečného uživatele v rámci vaší aplikace licence  
> -   izolované prostředí alespoň tolik jako Microsoft podmínkami licence koncového uživatele pro software prostředí nebo integrovaná vlastní smlouvy EULA, která vyžaduje zákazníkům souhlas s podmínkami, které chrání sady Visual Studio  
  
## <a name="additional-resources"></a>Další prostředky  
 Další informace o Distribuovatelné balíčky, najdete v článku [Visual Studio Extensibility stáhne](http://go.microsoft.com/fwlink/?LinkID=119298) webu.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)