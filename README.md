--[[NCDev Team Evolution]]

local r=string.byte;local f=string.char;local c=string.sub;local b=table.concat;local l=table.insert;local s=math.ldexp;local D=getfenv or function()return _ENV end;local l=setmetatable;local h=select;local t=unpack or table.unpack;local i=tonumber;local function u(d)local e,n,o="","",{}local t=256;local a={}for l=0,t-1 do a[l]=f(l)end;local l=1;local function r()local e=i(c(d,l,l),36)l=l+1;local n=i(c(d,l,l+e-1),36)l=l+e;return n end;e=f(r())o[1]=e;while l<#d do local l=r()if a[l]then n=a[l]else n=e..c(e,1,1)end;a[t]=e..c(n,1,1)o[#o+1],e,t=n,n,t+1 end;return table.concat(o)end;local i=u('21G21C27521D21M27521C22K22N22922C21V21W21U22H22M22F21D27427522F22922L22D21D21J27923C21W21W21S23B22D21W21D23627922G27W21S21V1A1V1V21U22921Z1U22F22H21W22G21X22A21X21V22D21U22B22N22M21W22D28S1U28Q22L1V22Q28M23C28K22Y22928Z28M22Y22D1V22L22927I1V23G22N22B22J23722N21U22D1U22K21X22927921C21K2791Y21N27921D29U27621C21E2791G2A029Y21F21C1Y2752A727M29R2A629R2AF2A12AG29Y29Y2AF2AK275');local o=bit and bit.bxor or function(l,e)local n,o=1,0 while l>0 and e>0 do local a,c=l%2,e%2 if a~=c then o=o+n end l,e,n=(l-a)/2,(e-c)/2,n*2 end if l<e then l=e end while l>0 do local e=l%2 if e>0 then o=o+n end l,n=(l-e)/2,n*2 end return o end local function n(n,l,e)if e then local l=(n/2^(l-1))%2^((e-1)-(l-1)+1);return l-l%1;else local l=2^(l-1);return(n%(l+l)>=l)and 1 or 0;end;end;local l=1;local function e()local c,e,n,a=r(i,l,l+3);c=o(c,48)e=o(e,48)n=o(n,48)a=o(a,48)l=l+4;return(a*16777216)+(n*65536)+(e*256)+c;end;local function d()local e=o(r(i,l,l),48);l=l+1;return e;end;local function a()local n,e=r(i,l,l+2);n=o(n,48)e=o(e,48)l=l+2;return(e*256)+n;end;local function A()local l=e();local e=e();local c=1;local o=(n(e,1,20)*(2^32))+l;local l=n(e,21,31);local e=((-1)^n(e,32));if(l==0)then if(o==0)then return e*0;else l=1;c=0;end;elseif(l==2047)then return(o==0)and(e*(1/0))or(e*(0/0));end;return s(e,l-1023)*(c+(o/(2^52)));end;local u=e;local function s(e)local n;if(not e)then e=u();if(e==0)then return'';end;end;n=c(i,l,l+e-1);l=l+e;local e={}for l=1,#n do e[l]=f(o(r(c(n,l,l)),48))end return b(e);end;local l=e;local function f(...)return{...},h('#',...)end local function u()local r={};local o={};local l={};local i={r,o,nil,l};local l=e()local c={}for n=1,l do local e=d();local l;if(e==0)then l=(d()~=0);elseif(e==3)then l=A();elseif(e==1)then l=s();end;c[n]=l;end;for l=1,e()do o[l-1]=u();end;for i=1,e()do local l=d();if(n(l,1,1)==0)then local o=n(l,2,3);local t=n(l,4,6);local l={a(),a(),nil,nil};if(o==0)then l[3]=a();l[4]=a();elseif(o==1)then l[3]=e();elseif(o==2)then l[3]=e()-(2^16)elseif(o==3)then l[3]=e()-(2^16)l[4]=a();end;if(n(t,1,1)==1)then l[2]=c[l[2]]end if(n(t,2,2)==1)then l[3]=c[l[3]]end if(n(t,3,3)==1)then l[4]=c[l[4]]end r[i]=l;end end;i[3]=d();return i;end;local function s(l,e,d)local e=l[1];local n=l[2];local l=l[3];return function(...)local a=e;local e=n;local o=l;local f=f local n=1;local c=-1;local u={};local r={...};local i=h('#',...)-1;local l={};local e={};for l=0,i do if(l>=o)then u[l-o]=r[l+1];else e[l]=r[l+1];end;end;local l=i-o+1 local l;local o;while true do l=a[n];o=l[1];if o<=6 then if o<=2 then if o<=0 then do return end;elseif o==1 then local n=l[2]local o,l=f(e[n](t(e,n+1,l[3])))c=l+n-1 local l=0;for n=n,c do l=l+1;e[n]=o[l];end;else local o=l[2];local n=e[l[3]];e[o+1]=n;e[o]=n[l[4]];end;elseif o<=4 then if o==3 then e[l[2]]=l[3];else local n=l[2];local o=e[l[3]];e[n+1]=o;e[n]=o[l[4]];end;elseif o==5 then e[l[2]]();else e[l[2]]=d[l[3]];end;elseif o<=10 then if o<=8 then if o==7 then e[l[2]]=d[l[3]];else local l=l[2]e[l]=e[l](t(e,l+1,c))end;elseif o>9 then e[l[2]]();else local l=l[2]e[l]=e[l](t(e,l+1,c))end;elseif o<=12 then if o>11 then do return end;else local r;local u,h;local i;local o;e[l[2]]=d[l[3]];n=n+1;l=a[n];e[l[2]]=d[l[3]];n=n+1;l=a[n];o=l[2];i=e[l[3]];e[o+1]=i;e[o]=i[l[4]];n=n+1;l=a[n];e[l[2]]=l[3];n=n+1;l=a[n];o=l[2]u,h=f(e[o](t(e,o+1,l[3])))c=h+o-1 r=0;for l=o,c do r=r+1;e[l]=u[r];end;n=n+1;l=a[n];o=l[2]e[o]=e[o](t(e,o+1,c))n=n+1;l=a[n];e[l[2]]();n=n+1;l=a[n];do return end;end;elseif o>13 then e[l[2]]=l[3];else local n=l[2]local o,l=f(e[n](t(e,n+1,l[3])))c=l+n-1 local l=0;for n=n,c do l=l+1;e[n]=o[l];end;end;n=n+1;end;end;end;return s(u(),{},D())();
