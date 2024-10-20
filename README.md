Practical No:01
Working with basic C# and ASP .NET
⦁	 Create an application that obtains four int values from the user and displays the product.

pract1a.aspx-
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server"><div>
<asp:Label ID="label1" runat="server">Enter First Number</asp:Label>
<asp:TextBox ID="textBox1" runat="server"></asp:TextBox><br />
<asp:Label ID="label2" runat="server">Enter Second Number</asp:Label>
<asp:TextBox ID="textBox2" runat="server"></asp:TextBox><br />
<asp:Label ID="label3" runat="server">Enter Third Number</asp:Label>
<asp:TextBox ID="textBox3" runat="server"></asp:TextBox><br />
<asp:Label ID="label4" runat="server">Enter Fourth Number</asp:Label>
<asp:TextBox ID="textBox4" runat="server"></asp:TextBox>
<br /><br />
<asp:Button ID="submit" runat="server" Text="Calculate"
onclick="submitButton_Click"/>
<br /><br />
<asp:Label ID="result" runat="server"></asp:Label>
</div></form></body>
</html>
  
pract1a.aspx.cs-
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void submitButton_Click(object sender, EventArgs e)
{
Int num1 = Convert.ToInt32(textBox1.Text.ToString()); int num2 = Convert.ToInt32(textBox2.Text.ToString()); int num3 = Convert.ToInt32(textBox3.Text.ToString()); int num4 = Convert.ToInt32(textBox4.Text.ToString());

int product = num1 * num2 * num3 * num4; result.Text = "Product of numbers : " + product;
}}
Output:


 	 


Create an application to demonstrate string operations.
Deafult.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="pract1b" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title>
</head>
<body>
<form id="form1" runat="server"><div>
<asp:Label ID="label1" runat="server">Enter First String</asp:Label>
<asp:TextBox ID="textBox1" runat="server" ></asp:TextBox>
<br /><br />
<asp:Label ID="label2" runat="server">Enter Second String</asp:Label>
<asp:TextBox ID="textBox2" runat="server"></asp:TextBox>
<br /><br />
<asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"

onselectedindexchanged="DropDownList1_SelectedIndexChanged">
<asp:ListItem >Concate</asp:ListItem>
<asp:ListItem>UpperCase</asp:ListItem>
<asp:ListItem>LowerCase</asp:ListItem>
<asp:ListItem>Reverse</asp:ListItem>
<asp:ListItem>Length</asp:ListItem>
<asp:ListItem>IsEmpty</asp:ListItem>
</asp:DropDownList>
<br /><br />
<asp:Button ID="Submit" runat="server" Text="Submit" onclick="Submit_Click" style="height: 26px" />
<br /><br />
<asp:Label ID="result" runat="server"></asp:Label>
</div>
</form>
</body>
</html>
Design
 

Default.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class pract1b : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void DropDownList1_SelectedIndexChanged(object sender, EventArgs e)
{
}
protected void Submit_Click(object sender, EventArgs e)
{
String str1 = textBox1.Text.ToString(); String str2 = textBox2.Text.ToString();
if (DropDownList1.SelectedItem.Text.Equals("Concate"))
{
result.Text = "Concatinate String : " + (str1 + str2);
}
else if (DropDownList1.SelectedItem.Text.Equals("UpperCase"))
{
result.Text = "<br>" + "Upper case of String :" + "<br>" + (str1.ToUpper() + " " + str2.ToUpper());
}
else if (DropDownList1.SelectedItem.Text.Equals("LowerCase"))
{
result.Text = "<br>" + "Lower case of String :" + "<br>" + str1.ToLower() + " " + str2.ToLower();
}
else if (DropDownList1.SelectedItem.Text.Equals("Length"))
{
result.Text = "<br>" + "Length of first string " + str1 + ":<br>" + str1.Length;
}
else if (DropDownList1.SelectedItem.Text.Equals("IsEmpty"))
{
if (String.IsNullOrEmpty(str1) && String.IsNullOrEmpty(str2))
{
result.Text = "<br>" + "Both the textbox is empty";

}
else if (String.IsNullOrEmpty(str1))
{
result.Text = "TextBox 1 is Empty";
}
else if (String.IsNullOrEmpty(str2))

{
result.Text = "TextBox 2 is Empty";
}
else
{
result.Text = "None of the TextBox is Empty";
} }
else
{
String reverse1 = new string(str1.Reverse().ToArray()); String reverse2 = new string(str2.Reverse().ToArray()); result.Text = "Reverse of 1st string :" + reverse1;
} }	}
Output:
  

Create an application to demonstrate following operations
i. Generate Fibonacci series. ii. Test for prime numbers.
iii. Test for vowels. iv. Use of foreach loop with arrays
v. Reverse a number and find sum of digits of a number.

Default.apsx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="pract1c" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">

<title></title>
</head><body>
<form id="form1" runat="server">
<div>
<asp:Label ID="label1" runat="server">Enter First String</asp:Label> &nbsp;&nbsp;&nbsp;
<asp:TextBox ID="textBox1" runat="server"></asp:TextBox><br />
<br />
select your operation :
<br />
<asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"
>
<asp:ListItem >Fibonacci</asp:ListItem>
<asp:ListItem>prime</asp:ListItem>
<asp:ListItem>vowels</asp:ListItem>
<asp:ListItem> foreach loop</asp:ListItem>
<asp:ListItem>Reverse and Find sum of Digit</asp:ListItem>
</asp:DropDownList>
<br /><br />
<asp:Button ID="Submit" runat="server" Text="Submit" onclick="Submit_Click"
/>
<br /><br />
<asp:Label ID="result" runat="server"> </asp:Label>
</div>
</form></body>
</html>
Design:
 

Deafult.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class pract1c : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Submit_Click(object sender, EventArgs e)
{
if (DropDownList1.SelectedItem.Text.Equals("Fibonacci"))
{
int usrInputNumber = Convert.ToInt32(textBox1.Text.ToString()); int firstNo = 0;
int secondNo = 1; int sum = 0;
Response.Write("fibonnaci series : " + firstNo + ", " + secondNo); int i = 2;
while (i < usrInputNumber)
{
sum = firstNo + secondNo; Response.Write(", " + sum); firstNo = secondNo; secondNo = sum;
i++;
}	}
else if (DropDownList1.SelectedItem.Text.Equals("prime"))
{
int num1 = Convert.ToInt32(textBox1.Text.ToString()); int i;
for (i = 2; i < num1 - 1; i++)
{
if (num1 % i == 0) break;
}

if (i < num1 - 1)
{
result.Text = "IS NOT A PRIME NUMBER";
}
else
{
result.Text = "A PRIME NUMBER";
}}
else if (DropDownList1.SelectedItem.Text.Equals("vowels"))
{
string str = textBox1.Text.ToString().ToLower(); int c = 0;
for (int i = 0; i < str.Length; i++)
{
if ((str.Substring(i, 1)) == "a" || (str.Substring(i, 1)) == "e" || (str.Substring(i, 1)) == "i" || (str.Substring(i, 1)) == "o" || (str.Substring(i, 1)) == "u")
{ c++;
} }
result.Text = ("Total number of vowels in " + str + " is " + c);
}
else if (DropDownList1.SelectedItem.Text.Equals("Reverse and Find sum of Digit"))
{
int num1 = Convert.ToInt32(textBox1.Text.ToString()); int reverse = 0;
int sum = 0;
while (num1 != 0)
{
int remainder = num1 % 10; reverse = reverse * 10 + remainder; sum = remainder + sum;
num1 = num1 / 10;
}
result.Text = "<br>" + "Reverse of entered number is " + reverse + "<br>" + "Sum of digits is" + sum;
}
else{
String s = textBox1.Text.ToString(); foreach (char c in s)

{
Response.Write("<br>" + c);
}	} } }
Output:
  
Practical No:02
Working with Object Oriented C# and ASP .NET
a) Create simple application to perform following operations
i. Finding factorial Value	ii. Money Conversion
iii. Quadratic Equation	iv. Temperature Conversion
Finding factorial Value
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="Default" %>
<!DOCTYPE	html	PUBLIC	"-//W3C//DTD	XHTML	1.0	Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div align="center">
<asp:Label ID="Label1" runat="server" Text="Enter a Number:"></asp:Label>
<asp:TextBox ID="TextBox1" runat="server" Width="147px"></asp:TextBox>
<br />
<asp:Button ID="Button1" runat="server" onclick="Button1_Click" Text="Factorial" /><br />
<asp:Label ID="Label2" runat="server"></asp:Label>
</div></form>
</body>
</html>
Design
 

Default.aspx.cs
using System;
using System.Collections.Generic;

using System.Linq; using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
int n = Int32.Parse(TextBox1.Text); int num, i, f = 1;
num = n;
for (i = 1; i <= n; i++)
{
f = f * i;
}
Label2.Text = "Factorial is: " + f.ToString();
}
}
Output:
 

Money Conversion a2.aspx
<%@	Page	Language="C#"	AutoEventWireup="true"	CodeFile="a2.aspx.cs" Inherits="a2" %>
<!DOCTYPE	html	PUBLIC	"-//W3C//DTD	XHTML	1.0	Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div align="center">

<asp:Label ID="Label1" runat="server" Text="Amount"></asp:Label>
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox><br />
<asp:Button ID="Button1" runat="server" onclick="Button1_Click" Text="Convert" /><br />
<asp:Label ID="Label2" runat="server" Text="Rupees to dollar"></asp:Label>
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<br />
<asp:Label ID="Label3" runat="server" Text="Dollar to rupees"></asp:Label>
<asp:TextBox ID="TextBox3" runat="server"></asp:TextBox>
<br />
<asp:Label ID="Label4" runat="server" Text="Rupees to Euro"></asp:Label>
<asp:TextBox ID="TextBox4" runat="server"></asp:TextBox>
<br />
<asp:Label ID="Label5" runat="server" Text="Euro to Rupees"></asp:Label>
<asp:TextBox ID="TextBox5" runat="server"></asp:TextBox>
</div></form>
</body>
</html> Design:
 

a2.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class a2 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
public class conv
{
public double d, r, e, a; public conv(double amount)
{
a = amount;
}
public void rtd()
{
d = a / 69;
}
public void dtr()
{
r = a * 69;
}
public void rte()
{
e = a / 82.36;
}
public void etr()
{
r = a * 82.36;
}
}
protected void Button1_Click(object sender, EventArgs e)
{
double a = Double.Parse(TextBox1.Text); conv obj = new conv(a);
obj.rtd();
TextBox2.Text = Convert.ToString(obj.d); obj.dtr();
TextBox3.Text = Convert.ToString(obj.r); obj.rte();
TextBox4.Text = Convert.ToString(obj.e); obj.etr();
TextBox5.Text = Convert.ToString(obj.r);
}
}
Output:

 
Temperature Conversion.	
a4.aspx-	 
<%@	Page	Language="C#" Inherits="a4" %>	AutoEventWireup="true"	CodeFile="a4.aspx.cs"
<!DOCTYPE	html	PUBLIC	"-//W3C//DTD	XHTML	1.0	Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div align="center">
<asp:Label ID="Label1" runat="server" Text="Celcius:"></asp:Label>
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox><br />
<asp:Button ID="Button1" runat="server" onclick="Button1_Click" Text="Celcius to Fahrenheit" /><br />
<asp:Label ID="Label2" runat="server" Text="Fahrenheit:"></asp:Label>
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<br /><br />
<asp:Label ID="Label3" runat="server" Text="Fahrenheit:"></asp:Label>
<asp:TextBox ID="TextBox3" runat="server"></asp:TextBox><br />
<asp:Button ID="Button2" runat="server" onclick="Button2_Click" Text="Fahrenheit to Celcius" /><br />
<asp:Label ID="Label4" runat="server" Text="Celcius:"></asp:Label>
<asp:TextBox ID="TextBox4" runat="server"></asp:TextBox>
</div></form></body>
</html>

Design-
 
a4.aspx.cs-
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class a4 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{ }
public class convert
{
public double temp, f, c; public convert(double t)
{
temp=t;
}
public void ctf()
{
f = ((temp * 9 / 5)) + 32;
}
public void ftc() {

c = ((temp - 32) * 5) / 9;
} }
protected void Button1_Click(object sender, EventArgs e)
{
double c = Double.Parse(TextBox1.Text); convert obj = new convert(c);
obj.ctf();
TextBox2.Text = obj.f.ToString();
}
protected void Button2_Click(object sender, EventArgs e)
{
double c = Double.Parse(TextBox3.Text); convert obj = new convert(c);
obj.ftc();
TextBox4.Text = obj.c.ToString();
} }
Output-
 

Practical No:03
Working with Web Forms and Controls

Create a simple web page with various sever controls to demonstrate setting and use of their properties. (Example : AutoPostBack)
 Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="Default" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server"><div>
<asp:Label ID="Label1" runat="server" Text="Name :"></asp:Label>
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
<br /><br />
<asp:Label ID="Label2" runat="server" Text="RNo."></asp:Label> &nbsp;:
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<br /><br />
<asp:Label ID="Label3" runat="server" Text="Class"></asp:Label>
&nbsp; :<asp:RadioButton ID="RadioButton1" runat="server" Text="FY" /> &nbsp;<asp:RadioButton ID="RadioButton2" runat="server" Text="SY" /> &nbsp;<asp:RadioButton ID="RadioButton3" runat="server" Text="TY" />
<br /><br />
<asp:Label ID="Label4" runat="server" Text="Course :"></asp:Label>
<asp:DropDownList ID="DropDownList1" runat="server" onselectedindexchanged="DropDownList1_SelectedIndexChanged" AutoPostBack="true">
<asp:ListItem>B.SC(IT)</asp:ListItem>
<asp:ListItem>M.SC(IT)</asp:ListItem>
<asp:ListItem>MCA</asp:ListItem>
</asp:DropDownList>
<br /><br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:Button ID="Button1" runat="server" Text="Submit" onclick="Button1_Click"/>

<br />
<asp:Label ID="Label5" runat="server"></asp:Label>
</div> </form> </body>
</html>
Output:
 

Default.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void DropDownList1_SelectedIndexChanged(object sender, EventArgs e)
{
Label5.Text = "You have been enrolled " + DropDownList1.SelectedItem;
}
protected void Button1_Click(object sender, EventArgs e)
{
string s;
if (RadioButton1.Checked == true)
{
s = RadioButton1.Text;
}

else if (RadioButton2.Checked == true)
{
s = RadioButton2.Text;
}
else
{
s = RadioButton3.Text;
}
Label5.Text = "You have been enrolled in " + s + " " + DropDownList1.SelectedItem;
} }
Output:
 
B)Demonstrate the use of Calendar control to perform following operations.
i) Display messages in a calendar control ii) Display vacation in a calendar control
iii) Selected day in a calendar control using style iv) Difference between two calendar dates
CalndrCntrl.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="CalndrCntrl.aspx.cs" Inherits="Calendar.WebForm1" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title>
<style type="text/css"> #form1 {
height: 407px;
}
</style></head>
<body>
<form id="form1" runat="server">
<div style="height: 585px">
<asp:Calendar ID="Calendar1" runat="server" BackColor="#FFFFCC" BorderColor="#FFCC66" BorderWidth="1px" DayNameFormat="Shortest" FirstDayOfWeek="Sunday" Font-Names="Verdana" Font-Size="8pt" ForeColor="#663399" Height="400px" NextPrevFormat="ShortMonth" OnDayRender="Calendar1_DayRender" ShowGridLines="True" Width="1000px">
<DayHeaderStyle BackColor="#FFCC66" Font-Bold="True" Height="1px" />
<NextPrevStyle BorderStyle="Solid" BorderWidth="2px" Font-Size="9pt" ForeColor="#FFFFCC" />
<OtherMonthDayStyle BackColor="#FFCC99" BorderStyle="Solid" ForeColor="#CC9966" />
<SelectedDayStyle BackColor="Red" Font-Bold="True" />
<SelectorStyle BackColor="#FFCC66" />
<TitleStyle BackColor="#990000" Font-Bold="True" Font-Size="9pt" ForeColor="#FFFFCC" />
<TodayDayStyle BackColor="#FFCC66" ForeColor="White" />
<WeekendDayStyle Height="50px" />
</asp:Calendar><br />
<asp:Label ID="Label1" runat="server"></asp:Label><br />
<asp:Label ID="Label2" runat="server"></asp:Label><br />
<asp:Label ID="Label3" runat="server"></asp:Label><br />
<asp:Label ID="Label4" runat="server"></asp:Label><br />
<asp:Label ID="Label5" runat="server"></asp:Label><br />
<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" style="margin-top: 0px" Text="RESULT" /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="RESET" />
<br />
</div>
</form>
</body>
</html>

Design:
 
CalndrCntrl.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls; namespace Calendar
{
public partial class WebForm1 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
Calendar1.Caption = "Vikas Pandey"; Calendar1.FirstDayOfWeek = FirstDayOfWeek.Sunday; Calendar1.NextPrevFormat = NextPrevFormat.ShortMonth; Calendar1.TitleFormat = TitleFormat.Month;
Label1.Text = "Your Selected Date:" + Calendar1.SelectedDate.ToString(); Label2.Text = "Todays Date:" + Calendar1.TodaysDate.ToShortDateString(); Label3.Text = "Ganpati Vacation Start: 09-13-2018";
TimeSpan d = new DateTime(2018, 09, 13) - DateTime.Now;
Label4.Text = "Days Remaining For Ganpati Vacation:" + d.Days.ToString(); TimeSpan d1 = new DateTime(2018, 12, 31) - DateTime.Now;
Label5.Text = "Days Remaining For New Year:" + d1.Days.ToString(); if (Calendar1.SelectedDate.ToShortDateString() == "09-13-2018")
Label3.Text = "<b>Ganpati Festival Start</b>";
if (Calendar1.SelectedDate.ToShortDateString() == "09-23-2018") Label3.Text = "<b>Ganpati Festival End<b>";
}
protected void Calendar1_DayRender(object sender, DayRenderEventArgs e)
{
if (e.Day.Date.Day == 15 && e.Day.Date.Month == 8)
{
e.Cell.BackColor = System.Drawing.Color.GreenYellow; Label lbl1 = new Label();
lbl1.Text = "<br>Independance Day!<br>"; e.Cell.Controls.Add(lbl1);
Image g1 = new Image(); g1.ImageUrl = "id.jpg"; g1.Height = 40;
g1.Width = 75; e.Cell.Controls.Add(g1);
}
if (e.Day.Date.Day == 5 && e.Day.Date.Month == 9)
{
e.Cell.BackColor = System.Drawing.Color.Yellow; Label lbl1 = new Label();
lbl1.Text = "<br>Teavhers Day!<br>"; e.Cell.Controls.Add(lbl1);
Image g1 = new Image(); g1.ImageUrl = "td.jpg"; g1.Height = 40;
g1.Width = 75; e.Cell.Controls.Add(g1);
}
if (e.Day.Date.Day == 13 && e.Day.Date.Month == 9)
{
Calendar1.SelectedDate = new DateTime(2018, 09, 12); Calendar1.SelectedDates.SelectRange(Calendar1.SelectedDate, Calendar1.SelectedDate.AddDays(10));
Label lbl1 = new Label(); lbl1.Text = "<br>Ganpati!<br>"; e.Cell.Controls.Add(lbl1); Image g2 = new Image(); g2.ImageUrl = "gc.jpg";

g2.Height = 40;
g2.Width = 75; e.Cell.Controls.Add(g2);
} }
protected void Button2_Click(object sender, EventArgs e)
{
Label1.Text = ""; Label2.Text = ""; Label3.Text = ""; Label4.Text = ""; Label5.Text = "";
Calendar1.SelectedDates.Clear();
} } }
Output:
 
C) Demonstrate the use of Treeview control perform following operations.
a) Tree view operations
Prac3b2.aspx

<%@ Page Language="C#" AutoEventWireup="true" CodeFile="prac3b2.aspx.cs" Inherits="prac3b2" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server"><div>
<asp:TreeView ID="TreeView1" runat="server" onselectednodechanged="TreeView1_SelectedNodeChanged" ShowLines="True" ontreenodecollapsed="TreeView1_TreeNodeCollapsed">
<Nodes>
<asp:TreeNode Text="I.T. Department" Value="I.T. Department">
<asp:TreeNode Text="Class Room" Value="Class Room">
<asp:TreeNode Text="601" Value="601"></asp:TreeNode>
<asp:TreeNode Text="602" Value="602"></asp:TreeNode>
</asp:TreeNode>
<asp:TreeNode Text="Lab" Value="Lab">
<asp:TreeNode Text="Lab-1" Value="Lab-1"></asp:TreeNode>
<asp:TreeNode Text="Lab-2" Value="Lab-2"></asp:TreeNode>
</asp:TreeNode>
</asp:TreeNode>
</Nodes>
</asp:TreeView>


</div></form>
</body></html>
Design:
 prac3b2.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class prac3b2 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void TreeView1_SelectedNodeChanged(object sender, EventArgs e)
{
Response.Write("You have selected the option:" + TreeView1.SelectedValue);
}
protected void TreeView1_TreeNodeCollapsed(object sender, TreeNodeEventArgs e)
{
Response.Write("The value Collapsed was:" + e.Node.Value);
}
}

Output:
 
⦁	Output after collapsing a value
 
⦁	Output after selecting a value
 

Practical No:04
Working with Form Controls
⦁	Create a Registration form to demonstrate use of various Validation controls.
WebForm1.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="_4a.WebForm1" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div>
<asp:Label ID="Label1" runat="server" Text="Your Name"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;& nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
<asp:RequiredFieldValidator ID="RequiredFieldValidator1" runat="server" ControlToValidate="TextBox1" ErrorMessage="Please Enter Your Name" ForeColor="Red"></asp:RequiredFieldValidator>
<br /><br />
<asp:Label ID="Label2" runat="server" Text="Enter Age"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;& nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<asp:RequiredFieldValidator ID="RequiredFieldValidator2" runat="server" ControlToValidate="TextBox2" ErrorMessage="Please Enter Your Age" ForeColor="Red"></asp:RequiredFieldValidator>
<asp:RangeValidator ID="RangeValidator1" runat="server" ControlToValidate="TextBox2" ErrorMessage="Enter Valid Age" ForeColor="Red" MaximumValue="100" MinimumValue="18" Type="Integer"></asp:RangeValidator>
<br /><br />
<asp:Label ID="Label3" runat="server" Text="Password"></asp:Label>
<asp:TextBox ID="TextBox3" runat="server" TextMode="Password"></asp:TextBox>

<asp:RequiredFieldValidator ID="RequiredFieldValidator3" runat="server" ControlToValidate="TextBox3" ErrorMessage="Please Enter Password" ForeColor="Red"></asp:RequiredFieldValidator>
<br /><br />
<asp:Label ID="Label4" runat="server" Text="Confirm Password"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox4" runat="server" TextMode="Password"></asp:TextBox>
<asp:RequiredFieldValidator ID="RequiredFieldValidator4" runat="server" ControlToValidate="TextBox4" ErrorMessage="Please Confirm Password" ForeColor="Red"></asp:RequiredFieldValidator>
<asp:CompareValidator ID="CompareValidator1" runat="server" ControlToCompare="TextBox3" ControlToValidate="TextBox4" ErrorMessage="Password Not Matched" ForeColor="Red"></asp:CompareValidator>
<br /><br />
<asp:Label ID="Label5" runat="server" Text="Email ID"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;& nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox5" runat="server"></asp:TextBox>
<asp:RequiredFieldValidator ID="RequiredFieldValidator5" runat="server" ControlToValidate="TextBox5" ErrorMessage="Please Enter Email Address" ForeColor="Red"></asp:RequiredFieldValidator>
<asp:RegularExpressionValidator ID="RegularExpressionValidator1" runat="server" ControlToValidate="TextBox5" ErrorMessage="Please Enter Valid Email Address" ForeColor="Red" ValidationExpression="\w+([-+.']\w+)*@\w+([-
.]\w+)*\.\w+([-.]\w+)*"></asp:RegularExpressionValidator>
<br /><br />
<asp:Label ID="Label6" runat="server" Text="Custom Text"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;& nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox6" runat="server"></asp:TextBox>
<asp:RequiredFieldValidator ID="RequiredFieldValidator6" runat="server" ControlToValidate="TextBox6" ErrorMessage="Please Enter Text" ForeColor="Red"></asp:RequiredFieldValidator>
<asp:CustomValidator ID="CustomValidator2" runat="server" ClientValidationFunction="ServerValidation" ControlToValidate="TextBox6" ErrorMessage="CustomValidator" ForeColor="Red"></asp:CustomValidator>
<br /><br />

<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Validate" />
<br />
<asp:Label ID="Label7" runat="server"></asp:Label>
<br />
<asp:ValidationSummary ID="ValidationSummary1" runat="server" />
</div></form>
</body>
</html>
 
Design:
WebForm1.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls; namespace _4a
{
public partial class WebForm1 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
if(Page.IsValid)
{
Label7.Text = "Thank You";
}
else
{
Label7.Text = "The text must be exactly 8 characters long!";
}
}
void ServerValidation(object source,ServerValidateEventArgs e)
{
if (e.Value.Length == 8) e.IsValid = true;
else
e.IsValid = false;
} } }
Output:
  


 


Create Web Form to demonstrate use of Adrotator Control.
WebForm1.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="_4b.WebForm1" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server"><div>
<asp:ScriptManager ID="ScriptManager1" runat="server">
</asp:ScriptManager><br />
<asp:Timer ID="Timer1" Interval="2000" runat="server">
</asp:Timer><br />
<asp:UpdatePanel ID="UpdatePanel1" runat="server">
</asp:UpdatePanel><br />
<asp:AdRotator ID="AdRotator1" runat="server" AdvertisementFile="~/XMLFile1.xml" Height="200px" Width="200px" />
<br /></div></form></body></html>
 
Design:
XMLFile1.xml
<?xml version="1.0" encoding="utf-8" ?>
<Advertisements><Ad>
<ImageUrl>~/v.png</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v1.png</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v2.jpg</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v3.jpg</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v4.jpg</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v5.jpg</ImageUrl>
</Ad><Ad>
<ImageUrl>~/v6.jpg</ImageUrl></Ad>
</Advertisements>
Output:
  
⦁	Create Web Form to demonstrate use User Controls. Defult.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>

<form id="form1" runat="server"><div><br />
<asp:Label ID="Label1" runat="server" Text="This is User Control"></asp:Label><br /><br />
&nbsp;&nbsp;
<asp:Label ID="Label2" runat="server" Text="Enter Your Name:"></asp:Label> &nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox><br /> &nbsp;&nbsp;
<asp:Label ID="Label3" runat="server" Text="Enter Your City: "></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox><br />
<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Save"
/><br />
<asp:Label ID="Label4" runat="server"></asp:Label><br />
</div></form></body>
</html>
Design :
 
Default.acpx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{	}
protected void Button1_Click(object sender, EventArgs e)
{
Label4.Text = "Your Name is " + TextBox1.Text + " and you are from " + TextBox2.Text;
}}
Output:
 

Practical No:05
Working with Navigation, Beautification and Master page. a)Create Web Form to demonstrate use of Website Navigation controls and Site Map.
Pract5a.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Pract5a.aspx.cs" Inherits="Practical5a.Pract5a" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div>
<asp:SiteMapDataSource ID="SiteMapDataSource1" runat="server" />
<br />
<asp:Menu ID="Menu1" runat="server" DataSourceID="SiteMapDataSource1">
</asp:Menu></div>
</form>
</body>
</html>
Design
 
Pract5a.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;

namespace Practical5a
{
public partial class Pract5a : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}}}
Web.sitemap
<?xml version="1.0" encoding="utf-8" ?>
<siteMap xmlns="http://schemas.microsoft.com/AspNet/SiteMap-File-1.0" >
<siteMapNode url="Pract5a.aspx" title="Home" description="Home page of our website">
<siteMapNode url="clsProp.aspx" title="Page2" description="Page2" />
<siteMapNode url="Default2.aspx" title="Page3" description="Page3" />
<siteMapNode url="Default3.aspx" title="Page4" description="Page4" />
</siteMapNode>
</siteMap>
⦁	Add 3 more .aspx files with “Welcome” message Output:
 	 
  

Create a web application to demonstrate use of Master Page with applying Styles and Themes for page beautification.

⦁	Adding Master Page
 

Adding Web page For Master page
 
MasterPage.master
<%@ Master Language="C#" AutoEventWireup="true" CodeFile="MasterPage.master.cs" Inherits="MasterPage" %>
<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title>Master Page</title>
<link href="css/my.css" rel="stylesheet" />
<asp:ContentPlaceHolder ID="head" runat="server">
</asp:ContentPlaceHolder>
<style type="text/css">
.auto-style1 { position: absolute; top: 373px;
left: 1028px; bottom: 303px;
}
.auto-style2 { position: absolute; top: 537px;
left: 1016px; z-index: 1;
}
</style></head>
<body>
<!DOCTYPE html>
<form id="form1" runat="server">
<html><head>
<title>Master</title>
<link rel="stylesheet" type="text/css" href="StyleSheet.css">
</head>
<body><header id="header">
<h1>Demo Of Master Page</h1>
</header>
<nav id="nav">
<ul>
<li><a href="home.aspx">Insight</a></li>
<li><a href="#">Products</a></li>
<li><a href="#">Downloads</a></li>
<li><a href="#">Contact Us</a></li>
</ul></nav>
<aside id="side">
<h1>Info</h1>
<a href="#"><p>Product Type 1</p></a>

<a href="#"><p>Product Type 2</p></a>
<a href="#"><p>Product Type 3<a href="#"><asp:ScriptManager ID="ScriptManager1" runat="server">
</asp:ScriptManager></a></p>
<asp:Button ID="Button2" runat="server" CssClass="auto-style1" style="z-index: 1" Text="Button" />
<asp:Button ID="Button1" runat="server" CssClass="auto-style2" Text="Button"
/>
</aside><div id="con">
<asp:ContentPlaceHolder ID="ContentPlaceHolder1" runat="server">
</asp:ContentPlaceHolder>
</div>
<footer id="footer"> copyright @Sambare
</footer></body>
</html></form>
</body></html>
MasterDisplay.aspx
<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPage.master" AutoEventWireup="true" CodeFile="MasterDisplay.aspx.cs" Inherits="MasterDisplay" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" runat="server">
<h1>Home page</h1>
</asp:Content> StyleSheet.css #header{ 
color: blueviolet; text-align: center; font-size: 20px; 
} 
#nav{ 
background-color:darkseagreen; padding: 5px; 
}

ul{
list-style-type: none;
}
li a { color:crimson ; font-size: 30px; column-width: 5%;
}li
{
display: inline; padding-left: 2px; column-width: 20px;
}
a{
text-decoration: none; margin-left:20px
}
li a:hover{
background-color: aqua; color:coral ; padding:1%;
}
#side{
text-align: center; float: right; width: 15%;
padding-bottom: 79%; background-color: #F1FAEE;
}
#article{
background-color: burlywood; padding: 10px;
padding-bottom: 75%;
}
#footer{
background-color: #C7EFCF; text-align:center;
padding-bottom: 5%; font-size: 20px;
}
#con{ border:double;
border-color:burlywood; }

Create a web application to demonstrate various states of ASP.NET Pages.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div style="height: 393px">
Username:<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<br /><br/>
Password:<asp:TextBox ID="TextBox3" runat="server"></asp:TextBox>
<br /><br/>
<asp:Button ID="Button4" runat="server" Text="submit" onclick="Button4_Click" />
&nbsp;&nbsp;
<asp:Button ID="Button5" runat="server" Text="restore" onclick="Button5_Click" />
<asp:HiddenField ID="HiddenField1" runat="server" />
<asp:Label ID="Label1" runat="server"></asp:Label><br/>
<asp:Label ID="Label2" runat="server" ></asp:Label><br/>
<asp:Button ID="Button1" runat="server" Text="ViewState" onclick="Button1_Click" /><br/><br/>
<asp:Button ID="Button2" runat="server" Text="HiddenField" onclick="Button2_Click" />
<br /><br />
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox><br /><br /><br />
<asp:Button ID="Button3" runat="server" Text="Cookies" onclick="Button3_Click" />
</div>
</form>
</body>
</html>

 
Design:
Deafult.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
if (IsPostBack)
{
if (ViewState["count"] != null)
{
int viewstateval = Convert.ToInt32(ViewState["count"]) + 1; Label1.Text = "ViewState:" + viewstateval.ToString(); ViewState["count"] = viewstateval.ToString();
} }
else {
ViewState["count"] = "1";
} }
protected void Button1_Click(object sender, EventArgs e)
{
Label2.Text = ViewState["count"].ToString();
}
protected void Button2_Click(object sender, EventArgs e)
{
Page.EnableViewState = true;
HiddenField1.Value = "welcome to our website:http://www.google.com" + "<br/>";
Label1.Text = HiddenField1.Value; HiddenField1.Value = "0";
int i = 0;
i = (int.Parse(HiddenField1.Value)) + 1; Label2.Text = i.ToString(); HiddenField1.Value = i.ToString();
}
protected void Button3_Click(object sender, EventArgs e)
{
HttpCookie c1 = new HttpCookie("name"); c1.Value = TextBox1.Text; Response.Cookies.Add(c1); Response.Redirect("Default2.aspx");
}
protected void Button4_Click(object sender, EventArgs e)
{
ViewState["name"] = TextBox2.Text; ViewState["password"] = TextBox3.Text; TextBox2.Text = TextBox3.Text = string.Empty;
}
protected void Button5_Click(object sender, EventArgs e)
{
if (ViewState["name"] != null)
{
TextBox2.Text = ViewState["name"].ToString();
}
if (ViewState["password"] != null)
{
TextBox3.Text = ViewState["password"].ToString();
}
} }
Default2.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class Default2 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
if (Request.Cookies["name"] != null)
{
Response.Write("Welcome:" + Request.Cookies["name"].Value);
}
}}
Output:
  
Practical No:06
Working with Database
⦁	Create a web application bind data in a multiline textbox by querying in another textbox.
Deafult.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title>
</head>
<body>
<form id="form1" runat="server">
<div>
<br /> &nbsp;&nbsp;&nbsp;
<asp:Button ID="Button1" runat="server" Text="Button" onclick="Button1_Click" />
<br /> &nbsp;&nbsp;
<asp:TextBox ID="TextBox1" runat="server" Text="<%# str %>" TextMode="MultiLine"></asp:TextBox>
&nbsp;<br />
<br /><br />
</div><br /><br />
</form>
</body></html>
 
Design:
Deafult.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls; using System.Data;
using System.Data.SqlClient;
public partial class _Default : System.Web.UI.Page
{
protected String str;
SqlConnection cn = new SqlConnection("Data Source=(LocalDB)\\MSSQLLocalDB;AttachDbFilename=F:\\jkwebsite\\pract6a2\
\App_Data\\Database.mdf;Integrated Security=True"); protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
SqlCommand cmd = new SqlCommand("select * from stud_dtls", cn); cn.Open();
SqlDataReader dr = cmd.ExecuteReader(); while (dr.Read())
{
str += dr["id"] + " " + dr["name"] + "\n";
}
this.DataBind();
} }

Query to create database
 
Output:
  

Create a web application to display records by using database.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" Debug="true" CodeFile="Default2.aspx.cs" Inherits="Default2" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div>
<asp:Label ID="Label1" runat="server" Text="Customer Details:"></asp:Label>
<br /><br />
<asp:Label ID="Label2" runat="server"></asp:Label>
<br /><br />
<asp:Button ID="Button1" runat="server" Text="Display records" OnClick="Button1_Click" />
&nbsp;&nbsp;
</div>
</form>
</body>
</html>
Design
 

Web .config
<configuration>
<system.web>
<compilation debug="true" strict="false" explicit="true" targetFramework="4.5"
/>
<httpRuntime targetFramework="4.5" />
</system.web>
<connectionStrings>
<add name="connStr" connectionString="Data Source=(LocalDB)\v11.0;AttachDbFilename=C:\Users\Deepak\Documents\Visual Studio 2012\WebSites\Prac 6b\App_Data\Database2.mdf;Integrated Security=True"/>
</connectionStrings>
</configuration>
Design.apsx.cs
using System; using System.Data;
using System.Collections.Generic; using System.Configuration; using System.Data.SqlClient; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class Default2 : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
string connStr = ConfigurationManager.ConnectionStrings["connStr"].ConnectionString; SqlConnection con = new SqlConnection(connStr);
SqlCommand cmd = new SqlCommand("Select * from customer", con); con.Open();
SqlDataReader reader = cmd.ExecuteReader(); while (reader.Read())

{
Label1.Text += reader["c_name"].ToString() + " " + reader["c_city"].ToString()
+ " " + reader["c_state"].ToString()+"<br>";
}
reader.Close(); con.Close();
} }
Output:
 

Demonstrate the use of Datalist link control.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div style="height: 310px">
<asp:DataList ID="DataList1" runat="server" DataSourceID="SqlDataSource1">
<ItemTemplate>
id:<asp:Label ID="idLabel" runat="server" Text='<%# Eval("id") %>' /><br /> name:<asp:Label ID="nameLabel" runat="server" Text='<%# Eval("name") %>'
/><br /><br />
</ItemTemplate>
</asp:DataList>
<asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" SelectCommand="SELECT * FROM [student]"></asp:SqlDataSource>
</div></form></body>
</html>

Design
 

Output:
 

Practical No:07
Create a web application to display Databinding using dropdownlist control.
Design
 

Web.config
<configuration>
<connectionStrings>
<add name="DatabaseConnectionString" connectionString="Data Source=(LocalDB)\v11.0;AttachDbFilename=&quot;C:\Users\Deepak\Documents\ Visual Studio 2012\WebSites\6c\App_Data\Database.mdf&quot;;Integrated Security=True;Connect Timeout=30"
providerName="System.Data.SqlClient" />
<add name="ConnectionString" connectionString="Data Source=(LocalDB)\v11.0;AttachDbFilename=|DataDirectory|\Database2.mdf;Integ rated Security=True"
providerName="System.Data.SqlClient" />
</connectionStrings>
<system.web>
<compilation debug="false" strict="false" explicit="true" targetFramework="4.5"
/>
<httpRuntime targetFramework="4.5" />
</system.web>
</configuration>
Default.aspx.cs
using System;
using System.Collections.Generic;

using System.Configuration; using System.Data.SqlClient; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
if (IsPostBack == false)
{
string DatabaseConnectionString = ConfigurationManager.ConnectionStrings["DatabaseConnectionString"].Connectio nString;
SqlConnection con = new SqlConnection(DatabaseConnectionString); SqlCommand cmd = new SqlCommand("select name from student", con); con.Open();
SqlDataReader reader = cmd.ExecuteReader(); DropDownList1.DataSource = reader; DropDownList1.DataTextField = "name"; DropDownList1.DataBind();
reader.Close(); con.Close();
} }
protected void Button1_Click(object sender, EventArgs e)
{
Label1.Text = "You have selected " + DropDownList1.SelectedValue;
}}
Output:
 
Create a web application for to display the phone no of an author using database.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br /><br />
<asp:Label ID="Label1" runat="server" Text="Enter Author's ID:"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
<br /><br />
<asp:Label ID="Label2" runat="server" Text="Author's Phone Number"></asp:Label>&nbsp;
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
<br /><br />
<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Button" /><br /><br />
<asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" DeleteCommand="DELETE FROM [authors] WHERE [author_id] = @author_id"

InsertCommand="INSERT INTO [authors] ([author_id], [phoneno]) VALUES (@author_id, @phoneno)" SelectCommand="SELECT * FROM [authors]" UpdateCommand="UPDATE [authors] SET [phoneno] = @phoneno WHERE [author_id] = @author_id">
<DeleteParameters>
<asp:Parameter Name="author_id" Type="Int32" />
</DeleteParameters>
<InsertParameters>
<asp:Parameter Name="author_id" Type="Int32" />
<asp:Parameter Name="phoneno" Type="Int32" />
</InsertParameters>
<UpdateParameters>
<asp:Parameter Name="phoneno" Type="Int32" />
<asp:Parameter Name="author_id" Type="Int32" />
</UpdateParameters>
</asp:SqlDataSource></div>
</form></body></html>
Design
 
Database:
 
Defult.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls; using System.Data;
using System.Data.SqlClient;
public partial class _Default : System.Web.UI.Page
{
SqlConnection cn = new SqlConnection("Data Source=(LocalDB)\\MSSQLLocalDB;AttachDbFilename=F:\\jkwebsite\\pract7b\\ App_Data\\Database.mdf;Integrated Security=True");
SqlDataReader dr;

protected void Page_Load(object sender, EventArgs e)
{	}
protected void Button1_Click(object sender, EventArgs e)
{
SqlCommand cmd = new SqlCommand("select * from authors where author_id="
+ TextBox1.Text + "", cn); cn.Open();
dr = cmd.ExecuteReader(); while (dr.Read())
{
TextBox2.Text = Convert.ToString(dr["phoneno"]);
}}}
Output:
 

Create a web application for inserting and deleting record from a database. (Using Execute-Non Query).
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="7c.aspx.cs" Inherits="_7c" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div style="height: 331px">
<asp:Label ID="Label1" runat="server" Text="Bank Address"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
<br />
<asp:Label ID="Label2" runat="server" Text="Bank City"></asp:Label>
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox><br />
<asp:Label ID="Label3" runat="server" Text="Bank Branch Name"></asp:Label> &nbsp;
<asp:TextBox ID="TextBox3" runat="server"></asp:TextBox><br />
<asp:Label ID="Label4" runat="server" Text="State"></asp:Label>
<asp:TextBox ID="TextBox4" runat="server"></asp:TextBox><br />
<asp:Label ID="Label5" runat="server" Text="ZIP Code"></asp:Label>
<asp:TextBox ID="TextBox5" runat="server"></asp:TextBox>
<br /><br />
<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Insert" />
&nbsp;&nbsp;&nbsp;&nbsp;
<asp:Button ID="Button2" runat="server" Text="Delete" />
<br /><br />
<asp:Label ID="Label6" runat="server"></asp:Label>
</div>
</form>
</body>
</html>
Design:
 
Default.aspx.cs
using System;
using System.Collections.Generic; using System.Configuration; using System.Data.SqlClient; using System.Linq;
using System.Web; using System.Web.UI; using System.Data;
using System.Web.UI.WebControls;
public partial class _7c : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
}
protected void Button1_Click(object sender, EventArgs e)
{
string connStr = ConfigurationManager.ConnectionStrings["connStr"].ConnectionString; SqlConnection con = new SqlConnection(connStr);
string InsertQuery = "insert into bank values(@b_add,@b_city,@b_name,@b_state,@b_zip)"; SqlCommand cmd = new SqlCommand(InsertQuery,con); cmd.Parameters.AddWithValue("@b_add", TextBox1.Text); cmd.Parameters.AddWithValue("@b_city", TextBox2.Text); cmd.Parameters.AddWithValue("@b_name", TextBox3.Text); cmd.Parameters.AddWithValue("@b_state", TextBox4.Text); cmd.Parameters.AddWithValue("@b_zip", TextBox5.Text); con.Open();
cmd.ExecuteNonQuery();
Label6.Text = "Record Inserted Successfully"; TextBox1.Text = "";
TextBox2.Text = ""; TextBox3.Text = ""; TextBox4.Text = ""; TextBox5.Text = ""; con.Close();
}
protected void Button2_Click(object sender, EventArgs e)

{
string connStr = ConfigurationManager.ConnectionStrings["connStr"].ConnectionString; SqlConnection con = new SqlConnection(connStr);
string deleteQuery = "delete from bank where b_add=@b_add"; SqlCommand cmd = new SqlCommand(deleteQuery, con); cmd.Parameters.AddWithValue("@b_add", TextBox1.Text); con.Open();
cmd.ExecuteNonQuery();
Label6.Text = "Record Deleted Successfully"; TextBox1.Text = "";
TextBox2.Text = ""; TextBox3.Text = ""; TextBox4.Text = ""; TextBox5.Text = ""; con.Close();
}}
Output:
  

Practical No:08
Working with data controls
Create a web application to demonstrate various uses and properties of SqlDataSource.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<title></title>
</head><body>
<form id="form1" runat="server">
<div><br /> &nbsp;
<asp:Label ID="Label1" runat="server" Text="Enter Your Roll_No:"></asp:Label>
&nbsp;<asp:TextBox ID="TextBox1" runat="server"></asp:TextBox><br />
<asp:Label ID="Label2" runat="server" Text="Enter Your Name:"></asp:Label> &nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox2" runat="server"></asp:TextBox><br />
<asp:Label ID="Label3" runat="server" Text="Enter Your Class:"></asp:Label> &nbsp;&nbsp;&nbsp;&nbsp;
<asp:TextBox ID="TextBox3" runat="server"></asp:TextBox><br /><br />
<asp:GridView ID="GridView1" runat="server" AutoGenerateColumns="False" DataKeyNames="rollno" DataSourceID="SqlDataSource1">
<Columns>
<asp:BoundField DataField="rollno" HeaderText="rollno" ReadOnly="True" SortExpression="rollno" />
<asp:BoundField DataField="Name" HeaderText="Name" SortExpression="Name" />
<asp:BoundField DataField="class" HeaderText="class" SortExpression="class"
/>
</Columns>
</asp:GridView><br /> &nbsp;

<asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Insert" />&nbsp;&nbsp;
<asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="Delete" /><br /><br /><br />
<asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" SelectCommand="SELECT * FROM [student]" DeleteCommand="DELETE FROM [student] WHERE [rollno] = @rollno" InsertCommand="INSERT INTO [student] ([rollno], [Name], [class]) VALUES (@rollno, @Name, @class)" UpdateCommand="UPDATE [student] SET [Name] = @Name, [class] = @class WHERE [rollno] = @rollno">
<DeleteParameters>
<asp:Parameter Name="rollno" Type="Int32" />
</DeleteParameters>
<InsertParameters>
<asp:Parameter Name="rollno" Type="Int32" />
<asp:Parameter Name="Name" Type="String" />
<asp:Parameter Name="class" Type="String" />
</InsertParameters>
<UpdateParameters>
<asp:Parameter Name="Name" Type="String" />
<asp:Parameter Name="class" Type="String" />
<asp:Parameter Name="rollno" Type="Int32" />
</UpdateParameters></asp:SqlDataSource>
<br /><br />
</div></form>
</body></html>
Design:
 

Web.config
<?xml version="1.0"?>
<!--
For more information on how to configure your ASP.NET application, please visit http://go.microsoft.com/fwlink/?LinkId=169433
-->
<configuration>
<connectionStrings>
<add name="ConnectionString" connectionString="Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=|DataDirectory|\Databas e.mdf;Integrated Security=True"
providerName="System.Data.SqlClient" />
</connectionStrings>
<system.web>
<compilation debug="true" targetFramework="4.5.2" />
<httpRuntime targetFramework="4.5.2" />
</system.web>
</configuration>

Default.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls; using System.Data;
using System.Data.SqlClient; using System.Configuration;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
string ConnectionString = ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString; SqlConnection con = new SqlConnection(ConnectionString);
SqlCommand cmd = new SqlCommand("Select * from student", con); con.Open();

SqlDataAdapter adapter = new SqlDataAdapter(cmd); DataSet ds = new DataSet();
adapter.Fill(ds, "student");
}
protected void Button1_Click(object sender, EventArgs e)
{
SqlDataSource1.InsertParameters["rollno"].DefaultValue = TextBox1.Text; SqlDataSource1.InsertParameters["Name"].DefaultValue = TextBox2.Text; SqlDataSource1.InsertParameters["class"].DefaultValue = TextBox3.Text; SqlDataSource1.Insert();
}
protected void Button2_Click(object sender, EventArgs e)
{
SqlDataSource1.DeleteParameters["rollno"].DefaultValue = TextBox1.Text; SqlDataSource1.Delete();
} }
Output:
 

⦁	Insert: Delete :
  

Create a web application to demonstrate data binding using DetailsView and FormView Control.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div align="center">
<asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" SelectCommand="SELECT * FROM [student]" ConflictDetection="CompareAllValues" DeleteCommand="DELETE FROM [student] WHERE [id] = @original_id AND (([name] = @original_name) OR ([name] IS NULL AND @original_name IS NULL))" InsertCommand="INSERT INTO [student] ([id], [name]) VALUES (@id, @name)" OldValuesParameterFormatString="original_{0}" UpdateCommand="UPDATE [student] SET [name] = @name WHERE [id] = @original_id AND (([name] = @original_name) OR ([name] IS NULL AND @original_name IS NULL))">
<DeleteParameters>
<asp:Parameter Name="original_id" Type="Int32" />
<asp:Parameter Name="original_name" Type="String" />
</DeleteParameters>
<InsertParameters>
<asp:Parameter Name="id" Type="Int32" />
<asp:Parameter Name="name" Type="String" />
</InsertParameters>
<UpdateParameters>
<asp:Parameter Name="name" Type="String" />
<asp:Parameter Name="original_id" Type="Int32" />
<asp:Parameter Name="original_name" Type="String" />
</UpdateParameters>
</asp:SqlDataSource>
<br />
<asp:DetailsView ID="DetailsView1" runat="server" AllowPaging="True"

DataSourceID="SqlDataSource1" Height="50px" Width="125px" AutoGenerateRows="False" DataKeyNames="id">
<Fields>
<asp:BoundField DataField="id" HeaderText="id" ReadOnly="True" SortExpression="id" />
<asp:BoundField DataField="name" HeaderText="name" SortExpression="name"
/>
<asp:CommandField ShowDeleteButton="True" ShowEditButton="True" ShowInsertButton="True" />
</Fields>
</asp:DetailsView><br />
<asp:SqlDataSource ID="SqlDataSource2" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" SelectCommand="SELECT * FROM [student]" ConflictDetection="CompareAllValues" DeleteCommand="DELETE FROM [student] WHERE [id] = @original_id AND (([name] = @original_name) OR ([name] IS NULL AND @original_name IS NULL))" InsertCommand="INSERT INTO [student] ([id], [name]) VALUES (@id, @name)" OldValuesParameterFormatString="original_{0}" UpdateCommand="UPDATE [student] SET [name] = @name WHERE [id] = @original_id AND (([name] = @original_name) OR ([name] IS NULL AND @original_name IS NULL))">
<DeleteParameters>
<asp:Parameter Name="original_id" Type="Int32" />
<asp:Parameter Name="original_name" Type="String" />
</DeleteParameters>
<InsertParameters>
<asp:Parameter Name="id" Type="Int32" />
<asp:Parameter Name="name" Type="String" />
</InsertParameters>
<UpdateParameters>
<asp:Parameter Name="name" Type="String" />
<asp:Parameter Name="original_id" Type="Int32" />
<asp:Parameter Name="original_name" Type="String" />
</UpdateParameters>
</asp:SqlDataSource><br />
<asp:FormView ID="FormView1" runat="server" AllowPaging="True" DataSourceID="SqlDataSource2" DataKeyNames="id">
<EditItemTemplate> id:
<asp:Label ID="idLabel1" runat="server" Text='<%# Eval("id") %>' /><br />
name:
<asp:TextBox ID="nameTextBox" runat="server" Text='<%# Bind("name") %>'
/><br />
<asp:LinkButton ID="UpdateButton" runat="server" CausesValidation="True" CommandName="Update" Text="Update" />
&nbsp;<asp:LinkButton ID="UpdateCancelButton" runat="server" CausesValidation="False" CommandName="Cancel" Text="Cancel" />
</EditItemTemplate>
<InsertItemTemplate> id:
<asp:TextBox ID="idTextBox" runat="server" Text='<%# Bind("id") %>' />
<br />
 name:
<asp:TextBox ID="nameTextBox" runat="server" Text='<%# Bind("name") %>'
/><br />
<asp:LinkButton ID="InsertButton" runat="server" CausesValidation="True" CommandName="Insert" Text="Insert" />
&nbsp;<asp:LinkButton ID="InsertCancelButton" runat="server" CausesValidation="False" CommandName="Cancel" Text="Cancel" />
</InsertItemTemplate>
<ItemTemplate>
id:<asp:Label ID="idLabel" runat="server" Text='<%# Eval("id") %>' /><br /> name:<asp:Label ID="nameLabel" runat="server" Text='<%# Bind("name") %>'
/><br />
<asp:LinkButton ID="EditButton" runat="server" CausesValidation="False" CommandName="Edit" Text="Edit" />
&nbsp;<asp:LinkButton ID="DeleteButton" runat="server" CausesValidation="False" CommandName="Delete" Text="Delete" /> &nbsp;<asp:LinkButton ID="NewButton" runat="server" CausesValidation="False" CommandName="New" Text="New" />
</ItemTemplate>
</asp:FormView>
</div>
</form>
</body>
</html>

Design.aspx
 

Default.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{ } }
Output:
 

Create a web application to display Using Disconnected Data Access and Databinding using GridView.
Default.aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1" runat="server">
<title></title></head>
<body>
<form id="form1" runat="server">
<div align="center">
<asp:GridView ID="GridView1" runat="server" AllowSorting="True" AutoGenerateColumns="False" DataSourceID="ObjectDataSource1" DataKeyNames="id">
<Columns>
<asp:BoundField DataField="id" HeaderText="id" SortExpression="id" ReadOnly="True" />
<asp:BoundField DataField="name" HeaderText="name" SortExpression="name"
/>
</Columns>
</asp:GridView><br />
<asp:ObjectDataSource ID="ObjectDataSource1" runat="server" InsertMethod="Insert" OldValuesParameterFormatString="original_{0}" SelectMethod="GetData" TypeName="DataSetTableAdapters.studentTableAdapter" DeleteMethod="Delete" UpdateMethod="Update">
<DeleteParameters>
<asp:Parameter Name="Original_id" Type="Int32" />
</DeleteParameters>
<InsertParameters>
<asp:Parameter Name="id" Type="Int32" />
<asp:Parameter Name="name" Type="String" />
</InsertParameters>
<UpdateParameters>
<asp:Parameter Name="name" Type="String" />
<asp:Parameter Name="Original_id" Type="Int32" />
</UpdateParameters>
</asp:ObjectDataSource>
</div></form></body>
</html>
Design:
⦁	Default.aspx	ii)DataSet.xsd
 
Default.aspx.cs
using System;
using System.Collections.Generic; using System.Linq;
using System.Web; using System.Web.UI;
using System.Web.UI.WebControls;
public partial class _Default : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{	}
}Output:
 

