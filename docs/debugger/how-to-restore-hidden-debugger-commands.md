---
title: 'Postupy: obnovení skrytých příkazů ladicího programu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, restoring commands
- debugging [Visual Studio], restoring commands
- commands, debugger
ms.assetid: 76ac9b77-f536-43b5-a9fc-984854b1c566
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e48e52f7d838b701745a449b979486b11a708faa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-restore-hidden-debugger-commands"></a>Postupy: Obnovení skrytých příkazů ladicího programu
Při instalaci sady Visual Studio, jste vyzváni k vyberte sadu výchozích nastavení IDE pro primární programovacího jazyka. Výchozí nastavení IDE pro některé jazyky mohou skrývat určité příkazů ladicího programu.  
  
 Pokud chcete používat funkce ladicího programu, která je skrytý na základě nastavení IDE výchozí, můžete přidat příkaz zpět do nabídky pomocí následujícího postupu.  
  
### <a name="to-restore-hidden-debugger-commands"></a>K obnovení skrytých příkazů ladicího programu  
  
1.  S projektem na otevřené **nástroje** nabídky, klikněte na tlačítko **přizpůsobit**.  
  
2.  V **přizpůsobit** dialogové okno, klikněte **příkazy** kartě.  
  
3.  V **řádku nabídek:** rozevíracího seznamu, vyberte **ladění** nabídky, která má obsahovat příkaz obnovený.  
  
4.  Klikněte **příkaz Přidat...**  tlačítko.  
  
5.  V **přidejte příkaz** , vyberte příkaz, který chcete přidat a klikněte na tlačítko **OK**.  
  
6.  Opakujte předchozí krok pro přidání jiného příkazu.  
  
7.  Klikněte na tlačítko **Zavřít** po dokončení přidávání příkazů do nabídky.  
  
    > [!WARNING]
    >  Některé položky nabídky se zobrazí, pouze když ladicího programu v konkrétní režimy, jako je například spuštění režimu nebo v režimu pozastavení. Položky, které jste přidali proto nemusí být okamžitě viditelné, po dokončení těchto kroků.  
  
## <a name="restoring-commands-not-available-from-the-customize-dialog-box"></a>Obnovení příkazů není k dispozici v dialogovém okně Upravit  
 Některé příkazy, především těch, které jsou součástí hierarchické nabídky, nelze obnovit z **přizpůsobit** dialogové okno. Chcete-li obnovit tyto příkazy, je nutné naimportovat novou kolekci nastavení IDE.  
  
#### <a name="to-import-new-ide-settings"></a>Chcete-li importovat nové nastavení IDE  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **nastavení importu a exportu**.  
  
2.  Na **Vítejte Průvodci importem a exportem nastavení** klikněte na tlačítko **importovat vybrané nastavení prostředí**a potom klikněte na **Další**.  
  
3.  Na **uložit aktuální nastavení** rozhodněte, zda se má uložit stávající nastavení a pak klikněte na **Další**.  
  
4.  Na **vyberte kolekce nastavení pro import** v části **výchozí nastavení** složky, vyberte kolekce nastavení pro vývoj, která má příkazy, které chcete použít. Pokud si nejste jisti kterou kolekci zvolte, zkuste **obecné nastavení vývoj** nebo **nastavení vývoje Visual C++**, které poskytují nejvíce příkazů ladicího programu.  
  
5.  Klikněte na tlačítko **Další**.  
  
6.  Na **zvolit nastavení pro import** v části **možnosti**, zajistěte, aby **ladění** je vybrána. Ostatní zaškrtávací políčka zrušte, pokud chcete importovat a tato nastavení.  
  
7.  Klikněte na tlačítko **Dokončit**.  
  
8.  Na **úplný Import** zkontrolujte chyby související s obnovením nastavení v části **podrobnosti**.  
  
9. Klikněte na tlačítko **Zavřít**.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)