---
title: AutoRecover, prostředí, dialogové okno Možnosti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59a28d73677011ef2de3ce4dd844757108b317ef
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55952408"
---
# <a name="autorecover-environment-options-dialog-box"></a>AutoRecover, prostředí, dialogové okno Možnosti

Pomocí této stránky v **možnosti** dialogové okno k určení, jestli se má automaticky zálohovat soubory nebo ne. Můžete také zadat, pokud chcete obnovit změněných souborů, pokud aplikace Visual Studio neočekávaně ukončí.

Přístup k tomuto dialogovému oknu výběrem **nástroje** nabídce vyberete **možnosti**a pak vyberete **prostředí** > **automatického obnovení**. Pokud se tato stránka nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** v **možnosti** dialogové okno.

**Ukládat informace automatického obnovení každých [n] minut**

Tuto možnost použijte, chcete-li přizpůsobit, jak často se automaticky uloží do souboru v editoru. Pro dříve uložené soubory, se uloží kopie souboru v *%USERPROFILE%\Documents\Visual Studio\\[verze] \Backup soubory\\[názevprojektu]*. Pokud jde o nový soubor a jeho ještě nebyly uloženy, soubor je automaticky uložené, pomocí názvu náhodně vygenerovaný soubor.

**Zachovat informace automatického obnovení dní [n]**

Tuto možnost použijte k určení, jak dlouho udržuje soubory vytvořené pro automatické Visual Studio.

### <a name="see-also"></a>Viz také:

- [Dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md)