
## PyNormaliz

Calculate the Hilbert basis from finite vectors.


```python
%matplotlib notebook
import PyNormaliz
import numpy as np
import matplotlib.pyplot as plt
vectors = [[2,1],[1,3]]
cone = PyNormaliz.NmzCone("cone",vectors)
HB = PyNormaliz.NmzResult(cone,"HilbertBasis")
fig,ax = plt.subplots()

# Plot vectors.
for v in vectors:
    ax.plot([0,v[0]],[0,v[1]],'k-')

xList = [x for x,y in HB]
yList = [y for x,y in HB]

# TODO: Complete fill_between function.
# x = np.arange(0,0.1,2)
# y1 = x*2
# y2 = x*3
# ax.fill_between(x,y1,y2,where=y2>=y1,facecolor='green', interpolate=True)

# Plot Hilbert basis.
ax.plot(xList,yList,'ro')
plt.show()
```


    <IPython.core.display.Javascript object>



<img src="data:image/png;base64,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Hkfg65mLL/CnmAEigAACKRMgABIArc3W7gC4ceNGHT58WO4uYKdOnazHEbh65uIL3CllQAgggIBnBAiABEBrM7YrALqJnocPHx557s/dBWT5UIC5+OgEBBBAAIFUCBAACYDWPos7ANbV1Wns2LEaPXq0tm3bZt2/r+uZi8/Xp4+DRwABBHwrQAAkAFqbN+4AuGvXLu3YsUPXrl1Tly5drPv3VT1z8fnqdHGwCCCAQGAFCIAEQGtzxxUAb9++rcGDB+vYsWOaOHGidd+er2cuPs+fIg4QAQQQCKUAAZAAaG38mAOg+1LDlClTlJ2drb1791r368l65uLz5GnhoBBAAAEEmggQAAmA1osi5gBYUlKiVatWqbq6Wt27d7fu1xP1zMXnidPAQSCAAAIIxClAACQAxtkyH1s9pgB479495eTkRO78uXf++nVhLj6/njmOGwEEEECgsQABkABovSJiCoBz5syRu1vm5v3z08JcfH46WxwrAggggECsAgRAAmCsvdLSem0GwOPHj2v+/PmRj3579+5t3V/S65mLL+nE7AABBBBAIM0CBEACoLUFWw2AtbW1GjRokNxbPxYuXGjdV1LqmYsvKaxsFAEEEEDAwwIEQAKgtT1bDYCLFy/WzZs3debMGWVkZFj3lZB65uJLCCMbQQABBBDwsQABkABobd8WA+D58+c1depUVVZWqm/fvtb9tLueufjaTUchAggggEBABQiABEBrazcbAB8/fqyhQ4fK3QEsKiqy7iOueubii4uLlRFAAAEEQihAACQAWtu+2QC4evVqlZaWqqysTB06dLDuo9V65uJLKi8bRwABBBAIoAABkABobeuPBcCKigqNGTNGFy9ejLz2LdELc/ElWpTtIYAAAgiETYAASAC09vxvBMDnz59r5MiRmj59ujZs2GDddqSeufgSwshGEEAAAQQQ+EiAAEgAtF4OvxEAt2zZov379+vy5cvKyspq97aZi6/ddBQigAACCCDQpgABkADYZpO0scJHAfC9997TsGHDdPbsWeXl5cW1Xebii4uLlRFAAAEEEDAJEADDEwDd57H/Q5ILbP8iaYmk6y10T3dJb0qa4j6BlXRC0lJJtc2sHwmADx480IwZM5Sbm6udO3e22ZTMxdcmESsggAACCCCQNAECYDgC4FeiAe7zkn4sab2keZJek/SrZrrLBb7fkjRb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">



```python

```