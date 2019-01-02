---
---
# <a name="view-recent-job-performance-and-details"></a>Zobrazit poslední výkon úlohy a podrobnosti

Po odeslání úloh můžete zobrazit seznam úloh, které chcete zobrazit jejich stav, dobu trvání a další.

1. V **Průzkumníka serveru**, rozbalte konkrétní výpočetní kontext.
2. Dvakrát klikněte na panel **úlohy**.
3. Zobrazí se seznam odeslaných do daného kontextu výpočetních úloh.
4. Vyberte konkrétní **úlohy** v seznamu zobrazíte podrobnosti.

![Monitorování úloh](media/job-details/monitor-jobs.png)

> Historie úlohy odeslané do virtuálních počítačů s Linuxem je uložen na virtuálním počítači v adresáři TMP. Proto pokaždé, když se bude vyžadovat restartování se vymaže historii úlohy. Trvalé záznamu historie úlohy nakonfigurujte prosím váš virtuální počítač jako výpočetní kontext v Azure Machine learning, pak odeslat úlohu do Azure Machine Learning (jako výpočetní kontext výběru virtuálního počítače).