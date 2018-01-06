---
title: "Visual Studio Tools for Unity konfigurace Azure návod | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: BAE62C27-CA7A-4466-8738-3DB880221CE1
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 25424ea06c01224bb1b35f783be82a857b991adf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="configure-easy-tables-in-azure"></a>Konfigurace snadno tabulek v Azure

Snadno tabulky jsou funkce [Azure Mobile Apps](https://azure.microsoft.com/services/app-service/mobile/) které umožňují instalaci a správu tabulek SQL přímo na portálu Azure grafickým uživatelským rozhraním. Azure Mobile Apps podporují řadu funkcí, ale rozsah tohoto příkladu je omezený na čtení a zápis dat uložených v back-end mobilní aplikace Azure z projektu Unity.

## <a name="create-a-new-azure-mobile-app"></a>Vytvoření nové mobilní aplikace Azure

Přihlaste se k [portál Azure](https://ms.portal.azure.com). Pokud nemáte předplatné Azure, [bezplatné zkušební verze](https://azure.microsoft.com/en-us/free/) nebo zahrnuté kredity z [Visual Studio Dev Essentials](https://www.visualstudio.com/dev-essentials/) více než postačí pro dokončení tohoto průvodce.

**Jednou v rámci portálu:**

1. Vyberte **nové > Web + mobilní > mobilní aplikace > vytvořit**.

  ![Vytvoření nové mobilní aplikace](media/vstu_azure-configure-easy-tables-image1.png)

2. Konfigurace nové mobilní aplikace:

  * **Název aplikace**. To bude vytvořena adresa URL použitá pro připojení k back-end mobilní aplikace Azure. Musíte zvolit jedinečný název, indikován zeleného zaškrtnutí.

  * **Předplatné**. Vyberte odběr, který nové mobilní aplikace bude používat pro fakturaci.

  * **Skupina prostředků**. Skupiny prostředků umožňují snadnější správu souvisejících prostředků. Ve výchozím nastavení vytvoří Azure novou skupinu prostředků se stejným názvem jako novou aplikaci. Ve výchozím nastavení funguje dobře pro průvodce.

  *  **Plán/umístění služby App Service**. Plán služby service určuje výpočetní výkon, umístění a náklady na prostředky, které využívá Azure k hostování nové mobilní aplikace. Ve výchozím nastavení vytvoří Azure nový plán služby s některé výchozí nastavení. Toto je nejjednodušší možnost pro účely tohoto postupu. Můžete však tato nabídka k přizpůsobení cenová úroveň nový plán služby nebo zeměpisné umístění. Kromě toho lze upravovat nastavení pro plán služby po jeho nasazení.

  ![Vytvoření nové mobilní aplikace](media/vstu_azure-configure-easy-tables-image2.png)

3. Vyberte **vytvořit** a poskytněte Azure a nasadit nový prostředek několik minut. Zobrazí se oznámení na portálu Azure a po dokončení nasazení.

## <a name="add-a-new-data-connection"></a>Přidat nové datové připojení

4. Po dokončení nasazení klikněte **všechny prostředky** tlačítko a potom vyberte nově vytvořenou mobilní aplikace.

  ![Vyberte nové mobilní aplikaci.](media/vstu_azure-configure-easy-tables-image3.png)

5. V okně nově otevřené přejděte dolů v levé nabídce straně a klikněte na tlačítko **snadno tabulky** tlačítko uvedený v seznamu **MOBILE** záhlaví.

  ![Vyberte snadno tabulky](media/vstu_azure-configure-easy-tables-image4.png)

6. Klepněte na modrou **muset nakonfigurovat rozhraní API pro snadný tabulky nebo snadná** Všimněte si zobrazení v horní části okna snadno tabulky.

  ![Klikněte na tlačítko Konfigurovat snadno tabulky oznámení](media/vstu_azure-configure-easy-tables-image5.png)

7. Klikněte na upozornění, která uvádí, že **potřebujete databáze pro použití snadno tabulky. Kliknutím sem vytvoříte jeden**.

  ![Klikněte na tlačítko vytvořit databázi upozornění.](media/vstu_azure-configure-easy-tables-image6.png)

8. V okně připojení dat klikněte na **přidat** tlačítko.

  ![Klikněte na tlačítko Přidat](media/vstu_azure-configure-easy-tables-image7.png)

9. Na stránce Přidat okno připojení dat, vyberte **SQL Database**.

  ![Vyberte databázi SQL](media/vstu_azure-configure-easy-tables-image8.png)

10. Otevře se okno pro konfiguraci nové databáze SQL a SQL server:

  * **Název**. Zadejte název databáze.

  * **Cílový server**. Klikněte na tlačítko **cílový server** otevřete okno nového serveru.

      * **Název serveru**. Zadejte název serveru.

      * **Přihlašovací jméno správce serveru a heslo**. Vytvořte uživatelské jméno a heslo pro správce serveru.

      * **Umístění**. Vyberte blízkým umístění serveru.

      * Ujistěte se, že **povolit službám azure přístup k serveru** zůstává zaškrtnuté políčko.

      * Klikněte na tlačítko **vyberte** k dokončení konfigurace serveru.

    * **Cenová úroveň**. Nechejte výchozí nastavení pro průvodce. To se dá později upravit.

    * **Kolace**. Ponechte výchozí nastavení.

    * Klikněte na tlačítko **vyberte** k dokončení konfigurace databáze.

    ![Konfigurace systému SQL server a databáze](media/vstu_azure-configure-easy-tables-image9.png)

11. Zpět v okně Přidat datové připojení klikněte na položku **připojovací řetězec**. Jakmile se zobrazí v okně připojovací řetězec, ponechejte výchozí nastavení a klikněte na tlačítko **OK**.

  ![Klikněte na tlačítko připojovací řetězec](media/vstu_azure-configure-easy-tables-image9.1.png)

12. Zpět v okně Přidat datové připojení text "MS_TableConnectionString" musí už být kurzívou. Klikněte na tlačítko **OK** a poskytněte Azure a několik minut pro vytvoření nové datové připojení. Po dokončení procesu dorazí oznámení.

  ![Klikněte na tlačítko OK](media/vstu_azure-configure-easy-tables-image9.2.png)

## <a name="complete-the-easy-table-initialization"></a>Dokončení inicializace snadno tabulky

13. Po úspěšném vytvoření nové datové připojení, klikněte na **všechny prostředky** tlačítko a znovu přejděte zpět do mobilní aplikace. Je důležité k dokončení tohoto kroku k aktualizaci konfigurace upozornění snadno tabulky.

14. Přejděte dolů a vyberte **snadno tabulky**a ještě jednou vybrat modrý **muset nakonfigurovat rozhraní API pro snadný tabulky nebo snadná** Všimněte si.

  ![Klikněte na tlačítko snadno tabulky oznámení](media/vstu_azure-configure-easy-tables-image5.png)

15. Tentokrát zobrazeném okně by mělo být uvedeno, "již máte data připojení" níže **1** záhlaví. V části **2** záhlaví, klikněte na zaškrtávací políčko, která uvádí, že **beru na vědomí, že tato akce přepíše obsah webu.** Klikněte na tlačítko **inicializace aplikace** a počkejte několik minut pro Azure a dokončete proces inicializace. Nové oznámení se oznamujeme po dokončení procesu.

  ![Klikněte na možnost inicializace aplikace](media/vstu_azure-configure-easy-tables-image10.png)

## <a name="next-step"></a>Další krok

* [Vytvoření jednoduchých tabulek](visual-studio-tools-for-unity-azure-setup.md)
