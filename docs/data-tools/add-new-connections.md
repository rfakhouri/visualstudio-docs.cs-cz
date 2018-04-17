---
title: Přidat nové připojení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0355b4fe3c05fb089e6feaac5bb52ff7f3f56da0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="add-new-connections"></a>Přidat nové připojení

Zkontrolujte připojení k databázi nebo službu a prozkoumejte obsah databáze a schémat, pomocí **Průzkumníka serveru**, **Průzkumník cloudu**, nebo **Průzkumník objektů systému SQL Server**. Funkce systému windows, tyto se překrývá do určité míry. Základní rozdíly jsou:

- Průzkumník serveru

   Nainstalována ve výchozím nastavení v sadě Visual Studio. Slouží k testování připojení a zobrazení databáze systému SQL Server, všechny databáze, které mají poskytovatele ADO.NET, který je nainstalován a některé služby Azure. Také ukazuje nízké úrovně objekty, například čítače výkonu systému, protokoly událostí a fronty zpráv. Pokud zdroj dat nemá žádný zprostředkovatel ADO.NET, nezobrazí zde, ale když můžete nadále používat ji ze sady Visual Studio připojením prostřednictvím kódu programu.

- Průzkumník cloudu

   Nainstalujte tohoto okna ručně tak, že vyberete rozšíření sady Visual Studio **nástroje**, **rozšíření a aktualizace**, **Online**, **Visual Studio Markeplace**. Poskytuje specializované funkce pro zkoumání a připojení ke službám Azure.

- Průzkumník objektů systému SQL Server

   Nainstalované pomocí nástroje SQL Server Data Tools a viditelné v rámci **zobrazení** nabídky. Pokud ho nevidíte existuje, přejděte na **programy a funkce** v Ovládacích panelech, najděte sady Visual Studio a pak vyberte **změnu** znovu spusťte instalační program po zaškrtnutí políčka pro SQL Server Data Tools. Použití **Průzkumník objektů systému SQL Server** k zobrazení SQL databáze (v případě, že mají poskytovatele ADO.NET), vytvářet nové databáze, upravte schémat, vytvořit uložené procedury, získat připojovací řetězce, zobrazení dat a další. Databáze SQL, které mají nainstalován žádný poskytovatel technologie ADO.NET zde nezobrazí, ale můžete se pořád připojit k nim prostřednictvím kódu programu.

## <a name="add-a-connection-in-server-explorer"></a>Přidat připojení v Průzkumníku serveru

Chcete-li vytvořit připojení k databázi, klikněte na tlačítko **přidat připojení** ikonu v **Průzkumníka serveru**, nebo klikněte pravým tlačítkem na **Průzkumníka serveru** na **dat Připojení** uzel a vyberte možnost **přidat připojení**. Tady můžete také připojit k databázi na jiný server, SharePoint služby nebo služby Azure.

![Ikona nové připojení Průzkumníka serveru](../data-tools/media/raddata-server-explorer-new-connection-icon.png "ikonu raddata nové připojení Průzkumníka serveru")

Po výběru této možnosti **přidat připojení** dialogové okno. Zde jsme zadali název instance SQL serveru LocalDB.  

![Přidat nové připojení](../data-tools/media/raddata-add-new-connection-dialog.png "raddata přidat nové připojení, dialogové okno")  

## <a name="change-the-provider"></a>Změňte zprostředkovatele

Pokud je zdroj dat není co chcete použít, klikněte na tlačítko **změnu** vyberte nový zdroj dat nebo nového zprostředkovatele dat ADO.NET. Přihlašovací údaje, v závislosti na tom, jak jste nakonfigurovali požádat nového poskytovatele.

![Změňte zprostředkovatele dat AD0.NET](../data-tools/media/raddata-change-ad0.net-data-provider.png "raddata poskytovatel dat AD0.NET změny")

## <a name="test-the-connection"></a>Otestujte připojení

Po výběru zdroje dat, klikněte na tlačítko **Test připojení**. Pokud dojde k neúspěchu, musíte se k řešení podle dokumentaci od dodavatele.

![Testovací připojení](../data-tools/media/raddata-test-connection.png "raddata Test připojení")

Pokud úspěšný, jste připraveni vytvořit *zdroj dat*, což je termín sady Visual Studio, který skutečně znamená *datový model* založený na základní databázi nebo službu.

## <a name="see-also"></a>Viz také

[Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)