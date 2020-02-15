import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
data = pd.read_excel('test.xlsx')
data

#legenda:
#UPK - Uvidi, planiranje, kontrola						
#ALT - Altruizam
#REL - Religioznost
#PRIVP - Privrženost partneru
#RODIT - Kvalitet odnosa sa roditeljima
#RODB - Kontakt s rodbinom i podrška od strane rodbine
#PRIJAT - Kontakt s prijateljima i podrška od strane prijatelja

dimenzije_LHT      = ["UPK", "ALT", "REL", "PRIVP", "RODIT", "RODB", "PRIJAT"]
dimenzija_R2_adj = [0.177,  0.159, 0.077, 0.086,   0.067,   0.072,  0.098,   ]
tip_R2_adj       = [0.094,  0.135, 0.034, 0.039,   0.049,   0.065,  0.031,   ]

#basic
plt.figure(figsize=(15,5))
plt.style.use('seaborn-darkgrid')
plt.ylabel("R2 adj")
plt.xlabel("Dimenzije LHT")
plt.plot(dimenzije_LHT, dimenzija_R2_adj, label="dimenzije: X - znacajne su, O - nisu", marker="x")
plt.plot(dimenzije_LHT, tip_R2_adj, label="tipovi: X - znacajni su, o - nisu", marker="x")
plt.legend()
plt.show()

#df
df = pd.DataFrame({
    'dimenzije_LHT':['UVIDPK','ALTRU','RELIG','PRIVPAR','RODITELJI','RODBINA','PRIJATELJI'],
    'dimenzija_R2_adj':[0.177,0.159,0.077,0.086,0.067,0.072,0.098],
    'tip_R2_adj':[0.094,0.135,0.034,0.039,0.049,0.065, 0.031],
    
})
plt.figure(figsize=(15,5))

ax = plt.gca()

df.plot(kind='line',x='dimenzije_LHT',y='dimenzija_R2_adj',ax=ax)
df.plot(kind='line',x='dimenzije_LHT',y='tip_R2_adj', color='red', ax=ax)

plt.show()

#bar
plt.figure(figsize=(15,5))
plt.style.use('seaborn-darkgrid')
plt.ylabel("R2 adj")
plt.xlabel("Dimenzije LHT")
plt.bar(dimenzije_LHT, dimenzija_R2_adj, label="dimenzije", color="#2ca25f")
plt.bar(dimenzije_LHT, tip_R2_adj, label="tipovi", color="#99d8c9")
plt.legend()
plt.show()


#sort
tab_po_dim = data.sort_values(by="1Dimenzija (R2adj)", ascending= False)
tab_po_dim
plt.figure(figsize=(15,5))
plt.bar(dimenzije_LHT, tab_po_dim["1Dimenzija (R2adj)"], label="Dim")
plt.bar(dimenzije_LHT, tab_po_dim["2Tip (R2adj)"], label="Tip")
plt.title("sortirano")
plt.legend()
plt.show()

