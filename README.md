# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :
```
importnumpyas np
importmath
importscipy.stats
L=[int(i)fori ininput().split()]
N=len(L); M=max(L)
X=list();f=list()
fori inrange(M+1):
c =0
forj in range(N):
if L[j]==i:
c=c+1
f.append(c)
X.append(i)
sf=np.sum(f)
p=list()
fori inrange(M+1):
p.append(f[i]/sf)
mean=np.inner(X,p)
p=list();E=list();xi=list()
print("XP(X=x)Obs.FrExp.Frxi")
print("--------------------------")
forx inrange(M+1):
p.append(math.exp(-mean)*mean**x/math.factorial(x))
E.append(p[x]*sf)
xi.append((f[x]-E[x])**2/E[x])
print("%2.2f%2.3f%4.2f%3.2f%3.2f"%(x,p[x],f[x],E[x],xi[x]))
print("--------------------------")
cal_chi2_sq=np.sum(xi)
print("Calculated value ofChisquareis%4.2f"%cal_chi2_sq)
table_chi2=scipy.stats.chi2.ppf(1-.01,df=M)
print("Tablevalueof chisquare at1 levelis%4.2f"%table_chi2)
ifcal_chi2_sq<table_chi2:
print("Thegivendatacanbe fitted inpoisson Distributionat 1%LOS")
else:
print("Thegivendatacannotbefittedin PoissonDistribution at1% LOS")
```
 

# Output : 
<img width="640" height="469" alt="{A92C4325-FADD-4957-8E65-2EFEF548E872}" src="https://github.com/user-attachments/assets/a14aa89f-fc32-41e8-8d55-319052399e69" />



# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
