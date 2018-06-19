---
title: Podepisování balíčků VSIX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84166ed96fb49567f4ede3e8e0c4b7e8ba3cc814
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31142289"
---
# <a name="signing-vsix-packages"></a>Podepisování balíčků VSIX
Rozšíření sestavení nemusíte být podepsané před jejich spuštěním v sadě Visual Studio, ale je dobrým zvykem Uděláte to tak.  
  
 Pokud chcete zabezpečit rozšíření a ujistěte se, že nikdo neoprávněně nemanipuloval, přidáte do balíčku VSIX digitální podpis. Při podpisu VSIX VSIX instalační program zobrazí zprávu s upozorněním, že ho je podepsaná, plus další informace o podpisu sám sebe. Pokud obsah VSIX byly změněny a VSIX není podepsaný znovu, zobrazí instalační program VSIX, podpis není platný. Instalace nebyla zastavena, ale uživatel bude upozorněn.  
  
> [!IMPORTANT]
>  Od verze 2015, budou označeny VSIX balíčky podepsaná pomocí jakoukoli jinou hodnotu než SHA256 šifrování tak, že má neplatný podpis. VSIX instalace nezablokuje, ale uživatel se upozornění.  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>Podepisování VSIX s VSIXSignTool  
 Existuje SHA256 šifrování, podepisování nástroje, které jsou k dispozici z [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) na nuget.org v [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).  
  
#### <a name="to-use-the-vsixsigntool"></a>Chcete-li použít VSIXSignTool  
  
1.  Přidání vaší VSIX do projektu.  
  
2.  Klikněte na uzel projektu v Průzkumníku řešení klikněte pravým tlačítkem na výběr **přidat &#124; spravovat balíčky NuGet**.  Další informace o NuGet a přidání balíčků NuGet naleznete v příručce najdete v článku [NuGet dokumentace](/NuGet) a [uživatelského rozhraní Správce balíčků](/NuGet/Tools/Package-Manager-UI) témata.  
  
3.  Vyhledejte VSIXSignTool z VisualStudioExtensibility a nainstalujte balíček NuGet.  
  
4.  Teď můžete spustit VSIXSignTool z umístění místní balíčky projektu. Získáte v nápovědě nástroje příkazového řádku pro váš scénář podpisový (VSIXSignTool.exe /?).  
  
 Třeba se přihlásit s heslem chráněné soubor certifikátu:  
  
 /F přihlašovací VSIXSignTool.exe \<Soubor_certifikátu > /p \<heslo > \<VSIXfile >  
  
## <a name="see-also"></a>Viz také  
 [Odesílání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)