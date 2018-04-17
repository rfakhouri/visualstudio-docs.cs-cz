---
title: 'Postupy: aktualizace rozšíření sady Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c37f26ed8215bb7eac360c978ba902c8e95975ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-update-a-visual-studio-extension"></a>Postupy: aktualizace rozšíření sady Visual Studio
Rozšíření sady Visual Studio v systému můžete aktualizovat pomocí **rozšíření a aktualizace** nainstalovat aktualizovanou verzi. Pokud vytvoříte aktualizovanou verzi rozšíření, můžete se označují jako aktualizovat zvyšující číslo verze v manifestu VSIX.  
  
 Aktualizace se nainstalují při VSIX manifest příchozí rozšíření má stejné `ID` jako jeden nainstalovaný a vyššího `Version` číslo. Pokud `Version` číslo je stejná nebo nižší, nelze nainstalovat balíček. Pokud `ID` hodnoty neshodují, balíček, který dosud není nainstalován rozpoznán jako samostatné přípony.  
  
 Abyste líp zabránili konfliktům během vývoje, doporučujeme odinstalovat starší verze rozšíření v průběhu a odinstalujte nebo také další potenciálně konfliktní rozšíření zakázat.  
  
### <a name="to-update-an-extension-on-your-system"></a>Chcete-li aktualizovat rozšíření ve vašem systému  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace**.  
  
2.  V levém podokně klikněte na **aktualizace**.  
  
3.  V prostředním podokně klikněte na aktualizaci, kterou chcete nainstalovat.  
  
     Číslo verze aktualizované rozšíření se zobrazí v pravém podokně, společně s další informace.  
  
4.  V dolní části v pravém podokně, klikněte na tlačítko **aktualizace**.  
  
### <a name="to-publish-an-update-of-an-extension"></a>Chcete-li publikovat aktualizace rozšíření  
  
1.  V sadě Visual Studio otevřete řešení pro rozšíření, které chcete aktualizovat. Proveďte požadované změny.  
  
    > [!IMPORTANT]
    >  Nepodepsané že není získat všechna rozšíření uživatele aktualizovat automaticky. Vždy byste měli podepsat rozšíření.  
  
2.  V **Průzkumníku**, otevřete source.extension.manifest.  
  
3.  V Návrháři manifestu zvýšit hodnotu počtu **verze** pole.  
  
4.  Uložte řešení a sestavte jej.  
  
5.  Nahrát nový soubor VSIX (ve složce \bin\Debug\ projektu) do [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) webu.  
  
     Když uživatel, který používá starší verzi rozšíření otevře **rozšíření a aktualizace**, na novou verzi se objeví v **aktualizace** seznamu, za předpokladu, že tento nástroj je nastaven na automaticky vyhledat aktualizace.  
  
     Můžete povolit nebo zakázat automatické zjišťování aktualizací v dolní části **aktualizace** podokně (**povolí nebo zakáže automatické zjišťování dostupné aktualizace**), které změny **zkontrolovat aktualizace** nastavení v **Nástroje / možnosti / prostředí nebo rozšíření a aktualizace**.  
  
    > [!NOTE]
    >  Od verze Visual Studio 2015 Update 2, můžete zadat (v **Nástroje / možnosti / prostředí nebo rozšíření a aktualizace**) tom, zda má funkce Automatické aktualizace pro rozšíření na uživatele, všechna rozšíření uživatele nebo oba (výchozí nastavení).  
  
## <a name="see-also"></a>Viz také  
 [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Hledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)
