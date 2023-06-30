# daily_show_guest
## Introduction

we will start by looking at guests of the Daily Show from 1999 - 2015
and see how the occupations of the guests have changed over time.
:::

::: {.cell .code execution_count="9" id="gc8mQPGSCVfN"}
``` python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
:::

::: {.cell .markdown}
![stage](vertopal_961b170733f64c30b64f1f5415f49f90/58b32d5cb71ee1f349881e1873c96b39924be7f9.jpg)
:::

::: {.cell .code execution_count="10" id="SXTfE5ALCb_w"}
``` python
df = pd.read_csv('daily_show_guests_cleaned.csv')
```
:::

::: {.cell .code execution_count="11" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="yzIoYmaNChrJ" outputId="a246b205-94a3-488c-929d-bda4468ae98e"}
``` python
print(df.head())
```

::: {.output .stream .stdout}
       YEAR GoogleKnowlege_Occupation     Show   Group    Raw_Guest_List
    0  1999                     actor  1/11/99  Acting    Michael J. Fox
    1  1999                  Comedian  1/12/99  Comedy   Sandra Bernhard
    2  1999        television actress  1/13/99  Acting     Tracey Ullman
    3  1999              film actress  1/14/99  Acting  Gillian Anderson
    4  1999                     actor  1/18/99  Acting  David Alan Grier
:::
:::

::: {.cell .code execution_count="12" id="zclsrluxDJMK"}
``` python
sns.set_palette("Blues")
```
:::

::: {.cell .code execution_count="14" colab="{\"base_uri\":\"https://localhost:8080/\",\"height\":489}" id="Y4IGxHjpC81Q" outputId="25e89938-a29c-4f63-827b-13046d5166aa"}
``` python
# Create the crosstab DataFrame
pd_crosstab = pd.crosstab(df["Group"], df["YEAR"])

# Plot a heatmap of the table with no color bar and using the BuGn palette
sns.heatmap(pd_crosstab, cbar=False, cmap="BuGn", linewidths=0.3)

# Rotate tick marks for visibility
plt.yticks(rotation=0)
plt.xticks(rotation=90)

#Show the plot
plt.show()
plt.clf()
```

::: {.output .display_data}
![](vertopal_961b170733f64c30b64f1f5415f49f90/805302da3c7e5a104cabec370a525d486b5ebf97.png)
:::

::: {.output .display_data}
    <Figure size 640x480 with 0 Axes>
:::
:::

::: {.cell .code id="OPGUPEg7DU3C"}
``` python
```
:::
