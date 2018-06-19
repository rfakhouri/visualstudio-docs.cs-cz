---
title: Sada SDK Visual Studia | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3b6b75deb576e5cb4e23975e80428433fbbc143a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144275"
---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
Visual Studio SDK umožňuje rozšířit funkce aplikace Visual Studio nebo integrovat nové funkce v sadě Visual Studio. Můžete distribuovat rozšíření jiným uživatelům a také na Visual Studio Marketplace. Tady jsou některé způsoby, ve kterém můžete rozšířit Visual Studio:  
  
-   Přidat příkazy, tlačítka, nabídky a další prvky uživatelského rozhraní IDE  
  
-   Přidat nástroj windows pro nové funkce  
  
-   Rozšiřte IntelliSense pro daný jazyk nebo poskytovat technologii IntelliSense pro nové programovací jazyky  
  
-   Použijte k zajištění, že pomocné parametry a návrhy, které usnadňuje vývojářům psát kód lepší žárovek  
  
-   Povolit podporu pro nové jazyky  
  
-   Přidat do vlastního typu projektu  
  
-   Reach miliony vývojářů prostřednictvím Visual Studio Marketplace  
  
 Pokud jste nikdy zapsána rozšíření sady Visual Studio před, byste měli najít další informace o těchto funkcích a na [zahajuje se vyvíjet rozšíření Visual Studia](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="installing-the-visual-studio-sdk"></a>Instalace sady Visual Studio SDK  
 Visual Studio SDK je volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="whats-new-in-the-visual-studio-2017-sdk"></a>Co je nového ve Visual Studio 2017 SDK  
 Visual Studio SDK obsahuje některé nové funkce, jako je například formát v3 VSIX, jakož i nejnovější změny, které mohou vyžadovat aktualizace rozšíření. Další informace najdete v tématu [co je nového ve Visual Studio 2017 SDK](../extensibility/what-s-new-in-the-visual-studio-2017-sdk.md).  
  
## <a name="visual-studio-user-experience-guidelines"></a>Prostředí pro práci uživatelů sady Visual Studio  
 Získat skvělé tipy pro návrh uživatelského rozhraní pro rozšíření v [Visual Studio prostředí pro práci uživatelů](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
 Můžete také zjistěte, jak chcete-li toto rozšíření vypadají skvěle vysoké DPI zařízení pomocí našich [adresování problémy DPI](../extensibility/addressing-dpi-issues2.md) tématu.  
  
 Využít [bitové kopie služby a katalog](../extensibility/image-service-and-catalog.md) správy bitových kopií velký a podporu pro vysokou DPI a motivů.  
  
## <a name="finding-and-installing-existing-visual-studio-extensions"></a>Hledání a instalaci rozšíření stávající sadě Visual Studio  
 Můžete najít rozšíření sady Visual Studio v **rozšíření a aktualizace** dialog v **nástroje** nabídky. Další informace najdete v tématu [hledání a používání rozšíření Visual Studia](../ide/finding-and-using-visual-studio-extensions.md). Můžete také najít rozšíření v [Visual Studio Marketplace](https://marketplace.visualstudio.com/)  
  
## <a name="visual-studio-sdk-reference"></a>Visual Studio SDK – referenční informace  
 Můžete najít odkaz na Visual Studio SDK API v [referenční informace sady Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md).  
  
## <a name="visual-studio-sdk-samples"></a>Sada SDK Visual Studio – ukázky  
 Příklady s otevřeným zdrojem rozšíření VS SDK najdete na webu GitHub na [Visual Studio – ukázky](https://aka.ms/vs2015sdksamples). Toto úložiště GitHub obsahuje ukázky, které ilustrují různé rozšiřitelné funkce v sadě Visual Studio.  
  
## <a name="other-visual-studio-sdk-resources"></a>Další zdroje sady Visual Studio SDK  
 Pokud máte dotazy týkající se VSSDK nebo chcete sdílet své zkušenosti vývoje rozšíření, můžete použít [fórum rozšiřitelnosti Visual Studio](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) nebo [ExtendVS Gitter Chatroom](https://gitter.im/Microsoft/extendvs).  
  
 Můžete najít další informace v [VSX Arcana blog](http://blogs.msdn.com/b/vsx/) a počet blogy zapsaných správcem MVPs Microsoft:  
  
-   [Rozšíření oblíbených položek aplikace Visual Studio](http://geekswithblogs.net/sdorman/archive/2014/10/05/favorite-visual-studio-extensions.aspx)  
  
-   [Rozšíření sady Visual Studio](http://www.visualstudioextensibility.com/overview/vs/)  
  
-   [Rozšíření sady Visual Studio](http://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)   
 [Postupy: migrace rozšiřitelnost projektů na Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)   
 [Nejčastější dotazy: Převádění doplňků na VSPackage rozšíření](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)   
 [Správa více vláken ve spravovaném kódu](../extensibility/managing-multiple-threads-in-managed-code.md)   
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [Přidání příkazů na panely nástrojů](../extensibility/adding-commands-to-toolbars.md)   
 [Rozšíření a přizpůsobení okna nástrojů](../extensibility/extending-and-customizing-tool-windows.md)   
 [Editor a rozšíření služeb jazyk](../extensibility/editor-and-language-service-extensions.md)   
 [Rozšíření projektů](../extensibility/extending-projects.md)   
 [Rozšíření uživatelská nastavení a možnosti](../extensibility/extending-user-settings-and-options.md)   
 [Vytváření vlastních projektů a šablon položek](../extensibility/creating-custom-project-and-item-templates.md)   
 [Rozšíření vlastností a v okně Vlastnosti](../extensibility/extending-properties-and-the-property-window.md)   
 [Rozšíření dalšími částmi sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Použití a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Správa VSPackages](../extensibility/managing-vspackages.md)   
 [Izolované prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md)   
 [Přesouvání rozšíření Visual Studia](../extensibility/shipping-visual-studio-extensions.md)   
 [V sadě Visual Studio SDK](../extensibility/internals/inside-the-visual-studio-sdk.md)   
 [Podpora pro Visual Studio SDK](../extensibility/support-for-the-visual-studio-sdk.md)   
 [Archiv](../extensibility/archive.md)   
 [Referenční dokumentace sady Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md)
