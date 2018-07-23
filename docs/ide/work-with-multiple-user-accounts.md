---
title: Práce s několika uživatelskými účty
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64e51bd43d278eb681d08b785c2a7d0c9539ee23
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179694"
---
# <a name="work-with-multiple-user-accounts"></a>Práce s několika uživatelskými účty

Pokud máte více účtů Microsoft a/nebo pracovní nebo školní účty, můžete ho přidat vše do sady Visual Studio, takže mají přístup k prostředkům z libovolného účtu bez nutnosti přihlásit se k němu samostatně. Služby Azure, služby Application Insights, Team Foundation Server a Office 365 v současné době podporují moderní prostředí přihlásit. Další služby může být k dispozici odehrává.

Po přidání více účtů na jednom počítači tuto sadu účtů zpřístupní se, pokud se přihlásíte k sadě Visual Studio na jiném počítači. Je důležité si uvědomit, že i když přesouvat názvy účtů, není to přihlašovací údaje. Proto se výzva k zadání přihlašovacích údajů pro tyto účty poprvé pokusí použít svoje prostředky na nový počítač.

Tento návod ukazuje, jak přidat více účtů sady Visual Studio a tom, jak zjistit, že prostředky dostupné z těchto účtů se projeví v umístění, jako **přidat připojenou službu** dialogového okna, **Průzkumníka serveru** , a **Team Explorer**.

## <a name="sign-in-to-visual-studio"></a>Přihlášení k sadě Visual Studio

- Přihlaste se do sady Visual Studio pomocí účtu Microsoft nebo účtu organizace. Měli byste vidět vaše uživatelské jméno se zobrazí v horním okraji okna, podobně jako tato:

     ![Currentlly přihlášeného uživatele](../ide/media/vs2015_username.png)

### <a name="access-your-azure-account-in-server-explorer"></a>Přístup k účtu Azure v Průzkumníku serveru

Stisknutím klávesy **Ctrl**+**Alt**+**S** otevřete **Průzkumníka serveru**. Zvolte **Azure** ikonu a při rozšiřuje vám měly zobrazit prostředky k dispozici v účtu Azure, který je přidružený Identifikátor, který jste použili k přihlášení k sadě Visual Studio. Měl by se zobrazit něco jako toto: (s tím rozdílem, že se zobrazí vaše vlastní prostředky).

![Rozbalení uzlu nástroje Azure zobrazení Průzkumníka serveru](../ide/media/vs2015_serverexplorer.png)

Při prvním použití sady Visual Studio na konkrétní zařízení, dialogové okno se zobrazí pouze předplatná zaregistrovaný pod ID, které jste přihlášení k prostředí IDE s. Mít přístup k prostředkům pro všechny vaše účty přímo z **Průzkumníka serveru** kliknutím pravým tlačítkem na **Azure** uzlu a zvolíte **spravovat a filtrovat předplatná**a přidání své účty z ovládacího prvku pro výběr účtu. Jiný účet, můžete pak v případě potřeby klikněte na šipku dolů vyberte ze seznamu účtů a. Po výběru účtu, které odběry pod tímto účtem, které chcete zobrazit v můžete **Průzkumníka serveru**.

![Správa předplatných Azure dialogového okna](../ide/media/vs2015_manage_subs.png)

Při příštím otevření **Průzkumníka serveru**, materiál pro tohoto předplatného se zobrazí.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Přístup k vašemu účtu Azure přes dialogové okno Přidat připojenou službu

1. Vytvořte projekt aplikace UPW v jazyce C#.

1. Zvolte uzel projektu v **Průzkumníka řešení** a klikněte na tlačítko **přidat** > **připojenou službu**. **Přidat připojenou službu** průvodce se zobrazí a zobrazí seznam služeb v účtu Azure, který je spojen s vaším ID sady Visual Studio přihlášení. Všimněte si, že není muset přihlašovat samostatně do Azure. Však nutné se přihlásit na jiné účty při prvním pokusu o přístup k jejich prostředkům z daného počítače.

    > [!WARNING]
    > Pokud je to první vytváříte aplikace pro UPW v sadě Visual Studio v určitém počítači, zobrazí se výzva k aktivovat zařízení pro vývoj režimu tak, že přejdete do **nastavení** > **aktualizace a zabezpečení**  >  **Pro vývojáře** ve vašem počítači. Další informace najdete v tématu [aktivovat zařízení pro vývoj](/windows/uwp/get-started/enable-your-device-for-development).

### <a name="access_azure"></a> Přístup k Azure Active Directory ve webovém projektu

Azure AD umožňuje podporu pro koncového uživatele jednotné přihlašování ve webových aplikacích ASP.NET MVC nebo ověřování AD v rámci služeb webových rozhraní API. Ověření domény se liší od účtu ověřování jednotlivých uživatelů Uživatelé, kteří mají přístup k vaší doméně služby Active Directory můžete pomocí svých existujících účtů v Azure AD pro připojení k webovým aplikacím. Aplikace Office 365 můžete také použít ověřování domény. Tento údaj zobrazíte v akci, vytvořte webovou aplikaci (**souboru** > **nový projekt** > **jazyka C#** > **cloudu**  >  **Webové aplikace ASP.NET**). V **nový projekt ASP.NET** dialogovém okně zvolte **změna ověřování**. Průvodce ověřením se zobrazí a můžete zvolit jaký typ ověřování, který má použít v aplikaci.

![Změna ověřování dialogové okno pro ASP.NET](../ide/media/vs2015_change_authentication.png)

Další informace o různých druzích ověřování v technologii ASP.NET, naleznete v tématu [webové projekty ASP.NET vytvořit v sadě Visual Studio 2013](http://www.asp.net/visual-studio/overview/2013/creating-web-projects-in-visual-studio#orgauth) (informace o ověřování je stále relevantní pro aktuální verze sady Visual Studio).

### <a name="access-your-visual-studio-team-services-account"></a>Přístup k vašemu účtu Visual Studio Team Services

V hlavní nabídce zvolte **týmu** > **připojit k Team Foundation Server** zobrazíte **Team Exploreru** okna. Klikněte na **vybrat týmové projekty**a potom v seznamu v části **vyberte sady Team Foundation Server**, měli byste vidět adresu URL pro váš účet Visual Studio Team Services. Když vyberete adresa URL bude být přihlášení bez nutnosti opakovaně zadávat svoje přihlašovací údaje.

## <a name="add-a-second-user-account-to-visual-studio"></a>Přidejte druhý uživatelský účet do sady Visual Studio

Klikněte na šipku dolů vedle své uživatelské jméno v horním rohu sady Visual Studio. Klikněte na tlačítko **nastavení účtu** položky nabídky. **Account manažera** zobrazí se dialogové okno a účet přihlášení. Zvolte **přidat účet** odkaz v dolním rohu dialogového okna Přidat nový účet Microsoft nebo nový pracovní nebo školní účet.

![Nástroj pro výběr účtu Visual Studio](../ide/media/vs2015_acct_picker.png)

Postupujte podle zobrazených výzev a zadejte nové přihlašovací údaje účtu. Je vidět na následujícím obrázku **Account manažera** po jeho přidání uživatele *Contoso.com* pracovní účet.

![Účet správce](../ide/media/vs2015_accountmanager.gif)

## <a name="revisit-the-add-connected-services-wizard-and-server-explorer"></a>Návštěvě Průvodce přidání připojené služby a Průzkumník serveru

Teď přejděte na **Průzkumníka serveru** znovu, klikněte pravým tlačítkem na **Azure** uzlu a zvolte **spravovat a filtrovat předplatná**. Zvolte nový účet kliknutím šipku rozevíracího seznamu vedle aktuálního účtu a klikněte na tlačítko odběry, které chcete zobrazit v **Průzkumníka serveru**. Měli byste vidět všechny služby, které jsou přidružené k zadanému odběru. I když nejste přihlášení aktuálně pomocí druhého účtu Visual Studio IDE, jste přihlášeni k tomuto účtu služby a prostředky. Totéž platí pro **projektu** > **přidat připojenou službu** a **týmu** > **připojit k Team Foundation Server**.

## <a name="see-also"></a>Viz také:

- [Přihlášení k sadě Visual Studio](signing-in-to-visual-studio.md)
