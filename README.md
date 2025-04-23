# Application-form
In this Application-form the user gives their data by filling the application form .This application form is created using python (tkinter application) and the given data are stored in the 
DB browser and then the inserted data of many users will be stored and the specific column(section) of data should be visualized.

The python code for this project is:
from tkinter import*
from tkinter import ttk
from tkinter import messagebox
import sqlite3
conn = sqlite3.connect('girijeshDATABASE.db')
cursor = conn.cursor()
w=Tk()
w.title('Application Form')
w.state('zoomed')

menu=Menu(w)
file=Menu(menu)
edit=Menu(menu)

def ne():
    exec(open("connecting piechart to sqlite database.py").read())

''' connecting piechart to sqlite database.py:
      import sqlite3
      import matplotlib.pyplot as plt
      
      conn = sqlite3.connect('girijeshDATABASE.db')
      cursor = conn.cursor()
      
      cursor.execute("SELECT Category, COUNT(*) FROM AccountApplication GROUP BY Category")
      data = cursor.fetchall()
      
      labels = [row[0] for row in data]
      sizes = [row[1] for row in data]
      
      plt.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=90,shadow=True)
      plt.title('Category Distribution')
      plt.axis('equal')
      plt.show()'''
# put the upper commented code in new file (it's title ==> exec(open("title"))
    
def op():
    print("Open")
def cu():
    print("Cut")
def co():
    print("Copy")

menu.add_cascade(label='File',menu=file)
file.add_command(label='New File',command=ne)
file.add_separator()
file.add_command(label='Open',command=op)
menu.add_cascade(label='Edit',menu=edit)
edit.add_command(label='Cut',command=cu)
edit.add_separator()
edit.add_command(label='Copy',command=co)

na = StringVar()
dob = StringVar()
gn = IntVar()
qu = IntVar()
naf = StringVar()
nam = StringVar()
var1 = IntVar()
var2 = IntVar()
var3 = IntVar()
var4 = IntVar()
var5 = IntVar()
ai = StringVar()
re = IntVar()
pan = StringVar()
res = StringVar()

#cursor.execute("create table AccountApplication(Name,DateofBirth,Gender,Qualification,NameofFather,NameofMother,Nationality,MartialStatus,\
                          # CountryName,City,AnnualIncome,Religion,Category,PANno,NatureofBusiness)")

clist = ["India","Nepal","Srilanka","Bhutan","China","Pakistan","Afghanistan","Myanmar","Bangladesh","Maladives","Japan","United States of America","Mexico","Canada","United Arab Emirates","German","France","Spain"]
combo1 = ttk.Combobox(w,values=clist)
combo1.place(x=190,y=603)

clist1 = ["Chennai","Mumbai","Kolkata","Delhi","Columbo","Kamalia","Kasur","Herat","Barisal","Adducity","Kathmandu","Lalitpur","Thimphu","Paro","Munich","Washington DC","Tibet","Mexico's city","Palma","Dubai","Tokyo","Toronto"]
combo2 = ttk.Combobox(w,values=clist1)
combo2.place(x=80,y=663)

clist2 = ["General OC","BC","MBC","SC","ST"]
combo3 = ttk.Combobox(w,values=clist2)
combo3.place(x=900,y=243)

lb=Label(w,text="APPLICATION",font=("Algerian",25)).place(x=500,y=10)
lb1=Label(w,text="Name",font=("Algerian",15)).place(x=10,y=120)
lb2=Label(w,text="Date of Birth",font=("Algerian",15)).place(x=10,y=180)
lb3=Label(w,text="Gender",font=("Algerian",15)).place(x=10,y=245)
lb4=Label(w,text="Qualification",font=("Algerian",15)).place(x=10,y=305)
lb5=Label(w,text="Name of Father",font=("Algerian",15)).place(x=10,y=360)
lb6=Label(w,text="Name of Mother",font=("Algerian",15)).place(x=10,y=420)
lb7=Label(w,text="Nationality",font=("Algerian",15)).place(x=10,y=485)
lb8=Label(w,text="Martial Status",font=("Algerian",15)).place(x=10,y=540)
lb9=Label(w,text="Country Name",font=("Algerian",15)).place(x=10,y=600)
lbl=Label(w,text="City",font=("Algerian",15)).place(x=10,y=660)
lbl1=Label(w,text="Annual Income",font=("Algerian",15)).place(x=790,y=120)
lbl2=Label(w,text="Religion",font=("Algerian",15)).place(x=790,y=185)
lbl3=Label(w,text="Category",font=("Algerian",15)).place(x=790,y=240)
lbl4=Label(w,text="PAN no.",font=("Algerian",15)).place(x=790,y=300)
lbl5=Label(w,text="Nature of Business",font=("Algerian",15)).place(x=790,y=360)

txt=Entry(w,textvariable=na,font=("Britannic"),width=30).place(x=80,y=123)
txt2=Entry(w,textvariable=dob,font=("Britannic"),width=30).place(x=182,y=183)
rad1=Radiobutton(w,text="Male",font=("Britannic"),variable=gn,value=1).place(x=100,y=243)
rad2=Radiobutton(w,text="Female",font=("Britannic"),variable=gn,value=2).place(x=193,y=243)
rad3=Radiobutton(w,text="UG program",font=("Britannic"),variable=qu,value=1).place(x=190,y=303)
rad4=Radiobutton(w,text="PG program",font=("Britannic"),variable=qu,value=2).place(x=335,y=303)
rad5=Radiobutton(w,text="12th completed",font=("Britannic"),variable=qu,value=3).place(x=480,y=303)
txt3=Entry(w,textvariable=naf,font=("Britannic"),width=30).place(x=180,y=363)
txt4=Entry(w,textvariable=nam,font=("Britannic"),width=30).place(x=180,y=423)
chk1=Checkbutton(w,text="IN-INDIAN",font=("Britannic"),variable=var1)
chk1.place(x=160,y=483)
chk2=Checkbutton(w,text="OTHERS",font=("Britannic"),variable=var2)
chk2.place(x=283,y=483)
chk3=Checkbutton(w,text="Married",font=("Britannic"),variable=var3)
chk3.place(x=190,y=543)
chk4=Checkbutton(w,text="Unmarried",font=("Britannic"),variable=var4)
chk4.place(x=293,y=543)
chk5=Checkbutton(w,text="Divorced",font=("Britannic"),variable=var5)
chk5.place(x=415,y=543)
txt5=Entry(w,textvariable=ai,font=("Britannic"),width=30).place(x=970,y=123)
rad6=Radiobutton(w,text="Hindu",font=("Britannic"),variable=re,value=1).place(x=890,y=183)
rad7=Radiobutton(w,text="Christian",font=("Britannic"),variable=re,value=2).place(x=990,y=183)
rad8=Radiobutton(w,text="Muslim",font=("Britannic"),variable=re,value=3).place(x=1100,y=183)
txt6=Entry(w,textvariable=pan,font=("Britannic"),width=30).place(x=880,y=303)

listbox=Listbox(w,width=18,height=9)
listbox.place(x=1050,y=363)
cl=["Agriculture","Showroom","Restaurent","School","Markiting","Sports club","Share market"]
for i in cl:
    listbox.insert(0,i)
def sa():
    if gn.get()==1:
        co="Male"
    elif gn.get()==2:
        co="Female"
    print(co)

    if qu.get()==1:
        cr="UG"
    elif qu.get()==2:
        cr="PG"
    elif qu.get()==3:
        cr="12th completed"
    print(cr)

    if var1.get()==1:
        nat="IN-INDIAN"
    elif var2.get()==1:
        nat="OTHERS"
    print(nat)

    if var3.get()==1:
        mar="Married"
    elif var4.get()==1:
        mar="Unmarried"
    elif var5.get()==1:
        mar="Divorced"
    print(mar)

    cna=combo1.get()
    print(cna)
    city=combo2.get()
    print(city)
    cat=combo3.get()
    print(cat)

    if re.get()==1:
        rel="Hindu"
    elif re.get()==2:
        rel="Christian"
    elif re.get()==3:
        rel="Muslim"
    print(rel)

    nob=(listbox.get(listbox.curselection()))
    print(nob)
    cursor.execute("insert into AccountApplication(Name,DateofBirth,Gender,Qualification,NameofFather,NameofMother,Nationality,MartialStatus,\
                           CountryName,City,AnnualIncome,Religion,Category,PANno,NatureofBusiness)values(?,?,?,?,?,?,?,?,?,?,?,?,?,?,?)"\
                           ,(na.get(),dob.get(),co,cr,naf.get(),nam.get(),nat,mar,cna,city,int(ai.get()),rel,cat,int(pan.get()),nob))

    conn.commit()
    messagebox.showinfo("SAVE","SAVE THE RECORD")

    na.set("")
    dob.set("")
    gn.get()==0
    qu.get()==0
    naf.set("")
    nam.set("")
    var1.get()==0
    var2.get()==0
    var3.get()==0
    var4.get()==0
    var5.get()==0
    combo1.set("")
    combo2.set("")
    ai.set("")
    re.get==0
    combo3.set("")
    pan.set("")

btn=Button(w,text="SUBMIT",command=sa).place(x=985,y=550)

w.config(menu=menu)
w.mainloop()

The output images are uploaded as follow:
![Screenshot 2025-04-23 092941](https://github.com/user-attachments/assets/3b1ce137-0cf1-4f11-a699-6e6af68b9f4d)
![Screenshot 2025-04-23 093608](https://github.com/user-attachments/assets/f1665178-960f-4477-8818-3284acc43d4f)
![Screenshot 2025-04-23 093017](https://github.com/user-attachments/assets/833c8218-c4d6-4f4d-8db0-3880120a1ddf)
