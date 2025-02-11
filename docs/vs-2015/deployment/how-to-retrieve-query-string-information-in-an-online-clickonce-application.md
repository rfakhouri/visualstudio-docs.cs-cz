---
title: 'Postupy: Načtení informací řetězce dotazu do Online aplikace ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, query strings
- query strings, retrieving information
ms.assetid: 48ce098a-a075-481b-a5f5-c8ba11f63120
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 588ff95f90c6d85526dfe931e8f0b8ab439d9b94
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697584"
---
# <a name="how-to-retrieve-query-string-information-in-an-online-clickonce-application"></a>Postupy: Načtení informací řetězce dotazu do online aplikace ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*Řetězec dotazu* je část adresy URL začínající otazník (?), který obsahuje libovolné informace ve formě *název = hodnota*. Předpokládejme, že máte [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci s názvem `WindowsApp1` , která hostujete na `servername`, a vy chcete předávat hodnotu pro proměnnou `username` při spuštění aplikace. Vaše adresa URL může vypadat nějak takto:  
  
 `http://servername/WindowsApp1.application?username=joeuser`  
  
 Následující dva postupy ukazují, jak používat [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace za účelem získání informací řetězce dotazu.  
  
> [!NOTE]
> Pokud se spuštění vaší aplikace pomocí protokolu HTTP, namísto použití sdílené složky nebo místního systému souborů, můžete předat pouze informace v řetězci dotazu.  
  
 První procedura ukazuje jak vaše [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace můžete použít malou část kódu ke čtení těchto hodnot při spuštění aplikace.  
  
 Následující postup ukazuje, jak nakonfigurovat váš [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci MageUI.exe tak, aby mohl přijímat parametry řetězce dotazu. Je potřeba to udělat pokaždé, když publikujete aplikaci.  
  
> [!NOTE]
> Než provedete rozhodnutí pro tuto funkci povolit, najdete v části "Zabezpečení" dále v tomto tématu.  
  
 Informace o tom, jak vytvořit [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] naleznete v tématu nasazení pomocí Mage.exe nebo MageUI.exe [názorný postup: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
> [!NOTE]
> Spuštění v rozhraní .NET Framework 3.5 SP1, je možné předat argumenty příkazového řádku pro offline [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace. Pokud chcete zadat argumenty do aplikace, můžete předat parametry do souboru zástupce s. Rozšíření APPREF MS.  
  
### <a name="to-obtain-query-string-information-from-a-clickonce-application"></a>K získání informací řetězce dotazu z aplikace ClickOnce  
  
1. Umístěte následující kód ve vašem projektu. Aby tento kód funkce, budete muset mít odkaz na System.Web a přidejte `using` nebo `Imports` příkazy pro System.Web System.Collections.Specialized a System.Deployment.Application.  
  
     [!code-csharp[ClickOnceQueryString#1](../snippets/csharp/VS_Snippets_Winforms/ClickOnceQueryString/CS/Form1.cs#1)]
     [!code-vb[ClickOnceQueryString#1](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnceQueryString/VB/Form1.vb#1)]  
  
2. Volání funkce definované dříve k načtení <xref:System.Collections.DictionaryBase.Dictionary%2A> z parametrů řetězce dotazu, který je indexované podle názvu.  
  
### <a name="to-enable-query-string-passing-in-a-clickonce-application-with-mageuiexe"></a>Chcete-li povolit předávání do aplikace ClickOnce s MageUI.exe řetězce dotazů  
  
1. Otevřete okno příkazového řádku .NET a zadejte:  
  
    ```  
    MageUI  
    ```  
  
2. Z **souboru** nabídce vyberte možnost **otevřete**a otevřete manifest nasazení pro váš [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace, což je soubor končící na `.application` rozšíření.  
  
3. Vyberte **možnosti nasazení** panelu v levém navigačním okně a vyberte **parametry povolit adresu URL, které se mají předat aplikaci** zaškrtávací políčko.  
  
4. Z **souboru** nabídce vyberte možnost **Uložit**.  
  
> [!NOTE]
> Alternativně můžete povolit předávání řetězce dotazů v [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]. Vyberte **parametry povolit adresu URL, které se mají předat aplikaci** zaškrtávací políčko, které lze najít otevřením **vlastnosti projektu**, vyberete **publikovat** kartu, kliknutím **Možnosti** tlačítko a pak vyberete **manifesty**.  
  
## <a name="robust-programming"></a>Robustní programování  
 Při použití parametrů řetězce dotazu, je třeba zadat pečlivě promyslet na tom, jak je aplikace nainstalovaná a aktivovaná. Pokud je aplikace nakonfigurována k instalaci na počítač uživatele z webu nebo ze sdílené síťové složce, je pravděpodobné, že uživatel aktivuje aplikaci jenom jednou prostřednictvím adresy URL. Poté uživatel obvykle aktivovat svoji aplikaci pomocí zástupce v **Start** nabídky. V důsledku toho vaše aplikace je zaručeno, že přijímat argumenty řetězce dotazu pouze jednou během celé jeho životnosti. Pokud budete chtít uložit tyto argumenty v počítači uživatele pro budoucí použití, zodpovídáte za jejich ukládáním do bezpečným a zabezpečeným způsobem.  
  
 Pokud vaše aplikace je online pouze, je vždy aktivovat prostřednictvím adresy URL. I v tomto případě však vaše aplikace musí být zapsané do fungovat správně, pokud jsou parametry řetězce dotazu chybí nebo je poškozený.  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Povolit předání parametrů adresy URL vašeho [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci pouze v případě, že máte v úmyslu čistí vstup všechny znaky škodlivý před jeho použitím. Řetězec vložených s uvozovky, lomítka nebo středníkem, třeba, můžou provádět operace s daty libovolného pokud použili nefiltrovaná v dotazu SQL na databázi. Další informace o zabezpečení řetězců dotazů, najdete v části [přehled zneužije skriptů](https://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
