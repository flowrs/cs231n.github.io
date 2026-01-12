# lecture_15

Extracted using pdfplumber



---
## Page 1
---


Spring 2025
Stanford CS231n 10th Anniversary
Lecture 15: 3D Vision
Jiajun Wu
May 22, 2025

[Page contains 1 image(s)]


---
## Page 2
---



[Page contains 1 image(s)]


---
## Page 3
---



[Page contains 1 image(s)]


---
## Page 4
---



[Page contains 1 image(s)]


---
## Page 5
---


Many Ways to Represent Geometry
•
Explicit
• Point cloud
• Polygon mesh
• Subdivision, NURBS
• …
•
Implicit
• Lever sets
• Algebraic surface
• Distance functions
• …
•
Each choice best suited to a different task/type of geometry
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 6
---


Representation Considerations
•
Needs to be stored in the computer
•
Creation of new shapes
• Input metaphors, interfaces…
•
Operations
• Editing, simplification, smoothing, filtering, repairing…
•
Rendering
• Rasterization, ray tracing, neural rendering…
•
Animation

---
## Page 7
---


Points
Points
Poin• Pto iCntsl =o uundordsered set of 3-tuples
• Often converted to other reps
• Meshes, implicits, parametric surfaces
• Simples•t Ereapsreiesre ntota ptiroonc: eosnsly, epdoiint tasn, dn/oo rc orennnedcetrivity
• Efficient point processing / modeling requires spatial
• (", $, %)
Collection of coordinates, possibly with normal
partitioning data structure
•
Points with orientation are called surfels
• Eg. to figure out neighborhoods
shading needs normals!
Shading needs normals!

[Page contains 1 table(s)]


### Table 1

|  |  | Points
ints
3-tuples
ps
etric surfaces
n, dn/oo rc orennnedcetrivity
modeling requires spatial
ossibly with normal
rfels
orhoods |  |
|  |  |  |  |
| Points
Poin• Pto iCntsl =o uundordsered set of 3-tuples
• Often converted to other reps
• Meshes, implicits, parametric surfaces
• Simples•t Ereapsreiesre ntota ptiroonc: eosnsly, epdoiint tasn, dn/oo rc orennnedcetrivity
• Efficient point processing / modeling requires spatial
• (", $, %)
Collection of coordinates, possibly with normal
partitioning data structure
•
Points with orientation are called surfels
• Eg. to figure out neighborhoods
shading needs normals!
Shading needs normals! | Points
oin• Pto iCntsl =o uundordsered set of 3-tuples
• Often converted to other reps
• Meshes, implicits, parametric surfaces
imples•t Ereapsreiesre ntota ptiroonc: eosnsly, epdoiint tasn, dn/oo rc orennnedcetrivity
• Efficient point processing / modeling requires spatial
(", $, %)
ollection of coordinates, possibly with normal
partitioning data structure
oints with orientation are called surfels
• Eg. to figure out neighborhoods
shading needs normals!
Shading needs normals! | ints
3-tuples
ps
etric surfaces
n, dn/oo rc orennnedcetrivity
modeling requires spatial
ossibly with normal
rfels
orhoods |  |


[Page contains 10 image(s)]


---
## Page 8
---


Output of Acquisition
Output of Acquisition
Slide credit: Hao Su

[Page contains 1 table(s)]


### Table 1

|  |  |  |
| O | Output of Acquisition
utput of Acquisition
Slide c | redit: Hao Su |


[Page contains 4 image(s)]


---
## Page 9
---


Points
Point Clouds
Points
•
Simplest representation: only points, no connectivity
• Standard 3D data from a variety of sources
• (", $, %)
Collection of coordinates, possibly with normal
• Often results from scanners
• Points with orientation are• cPaollteedn tsiuarlflye lns oisy
•
Often results from scanners
•
Potentially noisy
•
Registration of multiple images
set of raw scans
Set of raw scans
• Depth imaging (e.g. by triangulation)
• Registration of multiple images

[Page contains 1 table(s)]


### Table 1

|  |  | Points
Points
, no connectivity
3D data from a variety of sources
ossibly with normal
sults from scanners
rlflye lns oisy |  |
| Point Clouds
Points
•
Simplest representation: only points, no connectivity
• Standard 3D data from a variety of sources
• (", $, %)
Collection of coordinates, possibly with normal
• Often results from scanners
• Points with orientation are• cPaollteedn tsiuarlflye lns oisy
•
Often results from scanners
•
Potentially noisy
•
Registration of multiple images
set of raw scans
Set of raw scans
• Depth imaging (e.g. by triangulation)
• Registration of multiple images |  |  |  |
|  | Points
ion: only points, no connectivity
• Standard 3D data from a variety of sources
)
coordinates, possibly with normal
• Often results from scanners
on are• cPaollteedn tsiuarlflye lns oisy
canners
ple images
set of raw scans
Set of raw scans
• Depth imaging (e.g. by triangulation)
• Registration of multiple images | Points
, no connectivity
3D data from a variety of sources
ossibly with normal
sults from scanners
rlflye lns oisy |  |


[Page contains 9 image(s)]


---
## Page 10
---


Points
Point Clouds
Point Clouds
•
Easily represent any kind of geometry
• Simplest representation: only points, no connectivity
•
Useful for large datasets
• Collection of (x,y,z) coordinates, possibly with normals
• Difficult to draw in und•erPsoainmts pwleithd orreiegnitoantiosn are called surfels
• Several limitations:
• no simplification or subdivision
•
Other limitations: • no direct smooth rendering
• no topological information
• No simplification or subdivision
• No direction smooth rendering
• No topological information ?
or

[Page contains 1 table(s)]


### Table 1

|  |  | Points
uds
ry
sentation: only points, no connectivity
,y,z) coordinates, possibly with normals
egnitoantiosn are called surfels
ons: |  |
| Point Clouds
Point Clouds
•
Easily represent any kind of geometry
• Simplest representation: only points, no connectivity
•
Useful for large datasets
• Collection of (x,y,z) coordinates, possibly with normals
• Difficult to draw in und•erPsoainmts pwleithd orreiegnitoantiosn are called surfels
• Several limitations:
• no simplification or subdivision
•
Other limitations: • no direct smooth rendering
• no topological information
• No simplification or subdivision
• No direction smooth rendering
• No topological information ?
or |  |  |  |
|  | uds
Point Clo | uds |  |
|  | ny kind of geometry
• Simplest representation: only points, no connectivity
atasets
• Collection of (x,y,z) coordinates, possibly with normals
in und•erPsoainmts pwleithd orreiegnitoantiosn are called surfels
• Several limitations:
• no simplification or subdivision
• no direct smooth rendering
• no topological information
or subdivision
oth rendering
formation ?
or | ry
sentation: only points, no connectivity
,y,z) coordinates, possibly with normals
egnitoantiosn are called surfels
ons: |  |
|  |  |  |  |


[Page contains 7 image(s)]


---
## Page 11
---


Polygonal Meshes
Polygonal Meshes
• Boundary representations of objects
•
Boundary representations of objects
Slide credit: Hao Su

[Page contains 1 table(s)]


### Table 1

| Polygonal Meshes
lygonal Meshes
• Boundary representations of objects
undary representations of objects
Slide c |
|  |


[Page contains 6 image(s)]


---
## Page 12
---


A Large Triangle Mesh
A Large Triangle Mesh
DDaavvidid
DDigigiittaall MMiicchheellaannggeelol oP Prorjoejcetct
2288,,118844,,552266 vveerrtitciceess
5566,,223300,,334433 ttrriiaanngglelses
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| A | A Large Triangle Mesh
Large Triangle Mesh
DDaavvidid
DDigigiittaall MMiicchheellaannggeelol oP Prorjoejcetct
2288,,118844,,552266 vveerrtitciceess
5566,,223300,,334433 ttrriiaanngglelses
CS184/284A Ren Ng
Slide c | redit: Ren Ng |


[Page contains 3 image(s)]


---
## Page 13
---


A Very Large Triangle Mesh
A Very Large Triangle Mesh
Google Earth
Meshes reconstructed from satellite and aerial photography
Trillions of triangles
Slide credit: Ren Ng
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

|  |  |  |
|  | A Very Large Triangle Mesh
A Very Large Triangle Mesh
Google Earth
Meshes reconstructed from satellite and aerial photography
Trillions of triangles
Slide credit
CS184/284A Ren Ng | : Ren Ng |
|  |  |  |


[Page contains 5 image(s)]


---
## Page 14
---


Mesh Upsampling – Subdivision
Mesh Upsampling - Subdivision
Increase resolution via interpolation
Increase resolution via interpolation
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| M | Mesh Upsampling – Subdivision
esh Upsampling - Subdivision
Increase resolution via interpolation
Increase resolution via interpolation
CS184/284A Ren Ng
Slide c | redit: Ren Ng |


[Page contains 2 image(s)]


---
## Page 15
---


Mesh Downsampling – Simplification
Mesh Downsampling - Simplification
Decrease resolution; try to preserve shape/appearance
Decrease resolution; try to preserve shape/appearance
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| M | Mesh Downsampling – Simplification
esh Downsampling - Simplification
Decrease resolution; try to preserve shape/appearance
Decrease resolution; try to preserve shape/appearance
CS184/284A Ren Ng
Slide c | redit: Ren Ng |


[Page contains 2 image(s)]


---
## Page 16
---


Mesh Regularization
Mesh Regularization
Modify sample distribution to improve quality
Modify sample distribution to improve quality
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| M | Mesh Regularization
esh Regularization
Modify sample distribution to improve quality
Modify sample distribution to improve quality
CS184/284A Ren Ng
Slide c | redit: Ren Ng |


[Page contains 2 image(s)]


---
## Page 17
---


Points
Shape Representations
Non-parametric
Points Meshes

[Page contains 1 table(s)]


### Table 1

|  | Points
esentations
Points Meshes |
| Shape Representations
Non-parametric
Points Meshes | esentations
Points Meshes |


[Page contains 5 image(s)]


---
## Page 18
---


ParametPriacr aRmeeptrriecs Renetparetisoenntation
Parametric Representation
Parametric Representation
• Range of a function
• Range of a function
• Range of a function
Range of a function
• Surface in 3D:
•SuS • ru Sfrau fca ref c a eic ne in 3 in 3D D 3:: D:
Slide credit: Hao Su

[Page contains 2 table(s)]


### Table 1

|  |  |  |
| rametPriacr aRmeeptrriecs Renetparetisoenntation
Parametric Representation
Parametric Representation
• Range of a function
• Range of a function
• Range of a function
Range of a function
• Surface in 3D:
•SuS • ru Sfrau fca ref c a eic ne in 3 in 3D D 3:: D:
Slide c |  |  |
|  | ametPriacr aRmeeptrriecs Renetparetisoenntation
Parametric Representation
Parametric Representation
• Range of a function
• Range of a function
• Range of a function
Range of a function
• Surface in 3D:
•SuS • ru Sfrau fca ref c a eic ne in 3 in 3D D 3:: D:
Slide c | red |
|  |  |  |
|  |  |  |


### Table 2

|  |  |
|  |  |
|  |  |
|  |  |


[Page contains 9 image(s)]


---
## Page 19
---


Parametric Curves
PPPaaarrraaammmeeetttrrriiiccc CCCuuurrrvvveeesss
••• EEExxxaaammmpppllleee::: EEExxxpppllliiiccciiittt cccuuurrrvvveee///ccciiirrrcccllleee iiinnn 222DDD
Explicit curve/circle in 2D
Slide credit: Hao Su

[Page contains 1 table(s)]


### Table 1

| Parametric Curves
PPPaaarrraaammmeeetttrrriiiccc CCCuuurrrvvveeesss
••• EEExxxaaammmpppllleee::: EEExxxpppllliiiccciiittt cccuuurrrvvveee///ccciiirrrcccllleee iiinnn 222DDD
Explicit curve/circle in 2D
Sli |
|  |


---
## Page 20
---


PPaararammeetrtircic S Suurfrafacceess
Parametric Surfaces
• •SSphpehreer ein i n3 D3D
Sphere in 3D
Slide credit: Hao Su

[Page contains 1 table(s)]


### Table 1

| P | a | PPaararammeetrtircic S Suurfrafacceess
rametric Surfaces
• •SSphpehreer ein i n3 D3D
Sphere in 3D
Slide | c | redit: Hao Su |


[Page contains 4 image(s)]


---
## Page 21
---


Bézier Curves
Bézier curves
Piecewise Bézier
Slide credit: Ren Ng

[Page contains 2 image(s)]


---
## Page 22
---


BBéézziieerr SSuurrffaacceess ((EExxpplliicciitt))
Bézier Surfaces
UUssee tteennssoorr pprroodduucctt ooff BBéézziieerr ccuurrvveess ttoo ggeett aa ppaattcchh::
Use tensor product of Bézier curves to get a patch:
ssuurrffaaccee
ppaattcchh
Multiple Bézier patches form a surface.
MMuullttiippllee BBéézziieerr ppaattcchheess ffoorrmm aa ssuurrffaaccee
CCSS118844//228844AA RReenn NNgg
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| Bé | BBéézziieerr SSuurrffaacceess ((EExxpplliicciitt))
zier Surfaces
UUssee tteennssoorr pprroodduucctt ooff BBéézziieerr ccuurrvveess ttoo ggeett aa ppaattcchh::
Use tensor product of Bézier curves to get a patch:
ssuurrffaaccee
ppaattcchh
Multiple Bézier patches form a surface.
MMuullttiippllee BBéézziieerr ppaattcchheess ffoorrmm aa ssuurrffaaccee
CCSS118844//228844AA RReenn NNgg
Slide c | redit: Ren Ng |


[Page contains 4 image(s)]


---
## Page 23
---


Subdivision Curves (Explicit)
Alternative starting point for smooth curves: subdivision
Start with control polygon
Insert new vertex at each edge midpoint
Update vertex positions according to fixed rule
For careful choice of averaging rule, yields smooth curve
Subdivision Curves/Surfaces
• Corner-cutting (Chaikin): quadratic B-spline
Slide cribbed from Keenan Crane, cribbed from Don Fussell.
)ticilpxE(
secafruS
noisividbuS
)”egac
lortnoc“(
hsem
nogylop
esraoc
htiw
tratS
tnemele
hcae
edividbuS
gnigareva
lacol
aiv
secitrev
etadpU
:elur
elbissop
ynaM
)sdauq(
kralC-llumtaC
•
)selgnairt(
pooL
•
...
•
:seussi
nommoC
?gnitamixorppa
ro
gnitalopretni
•
?secitrev
ta
ytiunitnoc
•
ytiunitnoc
eetnaraug
ot
redrah
;gniledom
rof
ysae
ylevitaleR
gN
neR
A482/481SC

[Page contains 1 table(s)]


### Table 1

| Subdivision Curves (Explicit)
Alternative starting point for smooth curves: subdivision
Start with control polygon
Insert new vertex at each edge midpoint
Update vertex positions according to fixed rule |  |
| For careful choice of averaging rule, yields smooth curve
Subdivision Curves/Surfaces
• Corner-cutting (Chaikin): quadratic B-spline
Slide cribbed from Keenan Crane, cribbed from Don Fussell. |  |
|  |  |


[Page contains 6 image(s)]


---
## Page 24
---


Points
Shape Representations
Explicit
Non-parametric
Points Meshes
Parametric
Splines Subdivision
Surfaces

[Page contains 1 table(s)]


### Table 1

|  | Points
esentations
Explicit
Points Meshes |
| Shape Representations
Explicit
Non-parametric
Points Meshes
Parametric
Splines Subdivision
Surfaces | esentations
Explicit
Points Meshes |


[Page contains 7 image(s)]


---
## Page 25
---


“Explicit” Representations of Geometry
All points are given directly.
Generally:
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 26
---


EExxpplliicciitt SSuurrffaaccee –– SSaammpplliinngg IIss EEaassyy
Explicit Surface – Sampling Is Easy
ff((uu,, vv)) == ((((22 ++ ccooss uu)) ccooss vv,, ((22 ++ ccooss uu)) ssiinn vv,, ssiinn uu))
yy
WWWhhhaaattt pppoooiniinntttsss l illeiiee o oon nnt httihhs iisssu ssruufarrcffaaecc?ee??
(', ()
Just plug in values!
JJuusstt pplluugg iinn ((uu,,vv)) vvaalluueess!!
xx
zz
EEExxxpppllliiicccitiitt rrreeeppprerrseeessneetnnatttaaiottniioos nnmss ammkeaa kksoeem ssooe mmtaees kttsaa ssekkasssy ee.aassyy
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| Exp | EExxpplliicciitt SSuurrffaaccee –– SSaammpplliinngg IIss EEaassyy
licit Surface – Sampling Is Easy
ff((uu,, vv)) == ((((22 ++ ccooss uu)) ccooss vv,, ((22 ++ ccooss uu)) ssiinn vv,, ssiinn uu))
yy
WWWhhhaaattt pppoooiniinntttsss l illeiiee o oon nnt httihhs iisssu ssruufarrcffaaecc?ee??
(', ()
Just plug in values!
JJuusstt pplluugg iinn ((uu,,vv)) vvaalluueess!!
xx
zz
EEExxxpppllliiicccitiitt rrreeeppprerrseeessneetnnatttaaiottniioos nnmss ammkeaa kksoeem ssooe mmtaees kttsaa ssekkasssy ee.aassyy
Slide c | redit: Ren Ng |


[Page contains 2 image(s)]


---
## Page 27
---


Explicit Surface – Inside/Outside Test Hard
(3/4, 1/2, 1/4)
Is inside?
Some tasks are hard with explicit representations.
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 28
---


“Implicit” Representations of Geometry
“Implicit” Representations of Geometry
BaBsaesde odn ocnla scsliafysisnigfy pinogin tpsoints
•
Points satisfy some specified relationship.
• Points satisfy some specified relationship
! ! !
" + $ + % = 1
E.g., sphere: all points in 3D, where
2 2 2
E.g. sphere: all points in 3D, where x +y +z = 1
f(x,y)
+1
More genera0ll(y", ,f$(x, %,y),z=) 0= 0
More generally,
f = 0
0
-1
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| “Implicit” Representations of Geometry
plicit” Representations of Geometry
BaBsaesde odn ocnla scsliafysisnigfy pinogin tpsoints
•
Points satisfy some specified relationship.
• Points satisfy some specified relationship
! ! !
" + $ + % = 1
E.g., sphere: all points in 3D, where
2 2 2
E.g. sphere: all points in 3D, where x +y +z = 1
f(x,y)
+1
More genera0ll(y", ,f$(x, %,y),z=) 0= 0
More generally,
f = 0
0
-1
CS184/284A Ren Ng
Slide cr |
|  |


[Page contains 1 image(s)]


---
## Page 29
---


Implicit Surface – Sampling Can Be Hard
Implicit Surface – Sampling Can Be Hard
2 2
f(x, y, z) = (2 x2 + y2) + z 1
   
p y
WWhhaatt ppooinintst sl ieli eo no n0 (f"(x, $,y,,%z)) == 00??
x
z
SSoommee ttaasksks sa raer eh ahrda rwdi twh iitmhp ilmicipt lricepitr erseepnrteatsieonnst.ations
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| Imp | Implicit Surface – Sampling Can Be Hard
licit Surface – Sampling Can Be Hard
2 2
f(x, y, z) = (2 x2 + y2) + z 1
   
p y
WWhhaatt ppooinintst sl ieli eo no n0 (f"(x, $,y,,%z)) == 00??
x
z
SSoommee ttaasksks sa raer eh ahrda rwdi twh iitmhp ilmicipt lricepitr erseepnrteatsieonnst.ations
Slide c | redit: Ren Ng |


[Page contains 1 image(s)]


---
## Page 30
---


Implicit Surface – Inside/Outside Tests Easy
(3/4, 1/2, 1/4)
Is inside?
Just plug it in:
0(", $, %) = −1/8 < 0
Yes, inside.
Implicit representations make some tasks easy.
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 31
---


Algebraic Surfaces (Implicit)
AlgebAralgice bSruaricf aScuersfa (cIems p(Ilmicpitli)cit)
", $, %
SSuurrffaaccee isis z zeeror os este ot fo af pao plyonolymnioalm inia l in x., y, z
Surface is zero set of a polynomial in x, y, z
More complex shapes?
MMoorree ccoommpplelex xs hsahpaeps?es?
CS184/284A Ren Ng
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

| Alg |  | redit: Ren Ng |
|  | Algebraic Surfaces (Implicit)
ebAralgice bSruaricf aScuersfa (cIems p(Ilmicpitli)cit)
", $, %
SSuurrffaaccee isis z zeeror os este ot fo af pao plyonolymnioalm inia l in x., y, z
Surface is zero set of a polynomial in x, y, z
More complex shapes?
MMoorree ccoommpplelex xs hsahpaeps?es?
CS184/284A Ren Ng
CS184/284A Ren Ng
Slide c |  |
|  |  |  |


[Page contains 8 image(s)]


---
## Page 32
---


ConstCruocntsitvreu cStoivlied SGoeliodm Geetroym (eImtrpyl i(cImit)plicit)
Constructive Solid Geometry (Implicit)
CCoommbbinienC eimo immplibpciiltni cgeite iogmmepeoltimrcyie tv tigraye B ovomioale eBtaronyo ovlpeieaar naB tooioopnleseraanti oonpserations
Union Union
Difference Difference
IntersectionIntersection
BBoooolleeaann Be xoepxorpleesraseinoss neisox: npsr:essions:
CS184/284ACS184/284A Ren Ng Ren Ng
Slide credit: Ren Ng

[Page contains 2 table(s)]


### Table 1

|  |  |  |  |  |
| Con | Co
stru
CCoomm
BBooooll
CS184/ | nstCruocntsitvreu cStoivlied SGoeliodm Geetroym (eImtrpyl i(cImit)plic
ctive Solid Geometry (Implicit)
bbinienC eimo immplibpciiltni cgeite iogmmepeoltimrcyie tv tigraye B ovomioale eBtaronyo ovlpeieaar naB tooioopnleseraanti oonpserations
Union Union
Difference Differe
IntersectionIntersection
eeaann Be xoepxorpleesraseinoss neisox: npsr:essions:
284ACS184/284A Ren Ng
Slide c | it)
nce
Ren Ng
redit: Ren | Ng |


### Table 2

| CS184/ | 284ACS184/2 |


[Page contains 12 image(s)]


---
## Page 33
---


Distance Functions (Implicit)
Instead of Boolean, gradually blend surfaces together using
Distance functions:
Giving minimum distance (could be signed distance) from anywhere to object
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 34
---


Distance Functions (Implicit)
Example: Blending (linear interp.) a moving boundary

[Page contains 1 image(s)]


---
## Page 35
---


Scene of Pure Distance Functions (Not Easy!)
Scene of Pure Distance Functions (Not Easy!)
See http://iquilezles.org/www/material/nvscene2008/nvscene2008.htm

[Page contains 1 table(s)]


### Table 1

| Sce | ne of Pure Distance Functions (Not Ea
Scene of Pure Distance Functions (Not Easy!)
See http://iquilezles.org/www/material/nvscene2008/nvscene2008.htm | sy!) |


[Page contains 1 image(s)]


---
## Page 36
---


Points
Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 12 image(s)]


---
## Page 37
---


Level Set Methods (Implicit)
Implicit surfaces have some nice features (e.g., merging/splitting).
But hard to describe complex shapes in closed form
Alternative: store a grid of values approximating function
Surface is found where interpolated values equal zero.
Provides much more explicit control over shape (like a texture)
Slide credit: Ren Ng

[Page contains 1 image(s)]


---
## Page 38
---


Level Sets from Medical Data (CT, MRI, etc.)
Level Sets from Medical Data (CT, MRI, etc.)
Level sets encode, e.g., constant tissue density
Level sets encode, e.g., constant tissue density
CS184/284A Ren Ng
Slide credit: Ren Ng

[Page contains 1 table(s)]


### Table 1

|  |
| Level Sets from Medical Data (CT, MRI, etc.)
el Sets from Medical Data (CT, MRI, e
Level sets encode, e.g., constant tissue density
Level sets encode, e.g., constant tissue density
CS184/284A Ren Ng
Slide c |


[Page contains 1 image(s)]


---
## Page 39
---


Related Representation: Voxels
•
Binary thresholding the volumetric grid

[Page contains 3 image(s)]


---
## Page 40
---


Points
Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 41
---


AI + Geometry: Datasets

---
## Page 42
---


Princeton Shape Benchmark
•
1814 Models
•
182 Categories
Shilane et al, 2004

[Page contains 1 image(s)]


---
## Page 43
---


Datasets Prior to 2014

[Page contains 1 image(s)]


---
## Page 44
---


Datasets for 3D Objects
•
Large-scale Synthetic Objects: ShapeNet, 3M models
•
ModelNet: absorbed by ShapeNet
•
ShapeNetCore: 51.3K models in 55 categories
…
Chang et al. ShapeNet. arXiv 2015
Wu et al. 3D ShapeNets. CVPR 2015

[Page contains 95 image(s)]


---
## Page 45
---


Objverse (800K) and Objverse-XL (10M)
Deitke et al. 2022, 2023

[Page contains 1 image(s)]


---
## Page 46
---


Object Scan
•
10,933 RGBD scans
•
441 models
Choi et al, arXiv 2016

[Page contains 2 image(s)]


---
## Page 47
---


CO3D
•
19,000 videos
•
50 categories
Reizenstein et al. ICCV 2021

[Page contains 1 image(s)]


---
## Page 48
---


From Objects to Parts
Figure from the ShapeNet paper, Chang et al. arXiv 2015

[Page contains 1 image(s)]


---
## Page 49
---


Datasets for 3D Object Parts
Fine-grained Parts: PartNet
•
Fine-grained (+mobility)
•
Instance-level
•
Hierarchical
Mo et al. CVPR 2019. Slide credit: Hao Su

[Page contains 1 image(s)]


---
## Page 50
---


Datasets for Indoor 3D Scenes
Scanned Real Scenes: ScanNet Most recently:
• 2.5M Views in 1,500 RGBD scans • ARKitScenes,
• 3D camera poses • ScanNet++ (with DSLR images)
•
Surface reconstructions
•
Instance-level semantic segmentations
Dai et al. CVPR 2017

[Page contains 2 image(s)]


---
## Page 51
---


AI + Geometry: Tasks
• 5(6) 5(6|8)
or --- Generative models
• Learning (conditional) shape priors
• Shape generation, completion, & geometry data processing
• 5(8|6)
--- Discriminative models
• Learning shape descriptors
• Shape classification, segmentation, view estimation, etc.
•
Joint modeling of 3D and 2D data
• Large-scale 2D datasets & very good pretrained models
• Differentiable projection/back-projection & differentiable/neural rendering
•
Joint modeling of multi-modal data beyond visual (e.g., text)

---
## Page 52
---


Points
AI + Geometry: Which Representation?
Explicit Implicit (Eulerian)
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| AI + Geometry: Which Representation?
Explicit Implicit (Eulerian)
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 53
---


Multi-View CNN
Su et al. ICCV 2015

[Page contains 1 image(s)]


---
## Page 54
---


Multi-View CNN
View 1
View 2
View 3
View N
Su et al. ICCV 2015

[Page contains 2 image(s)]


---
## Page 55
---


Multi-View CNN
…
…
…
…
. .
.
CNN
1
CNN
1
CNN
1
CNN
1
CNN : a ConvNet extracting image features
1
Su et al. ICCV 2015

[Page contains 2 image(s)]


---
## Page 56
---


Multi-View CNN
…
…
…
…
CNN
1
. .
.
View
pooling
View pooling: element-wise
max-pooling across all views
Su et al. ICCV 2015

[Page contains 2 image(s)]


---
## Page 57
---


Multi-View CNN
…
…
…
…
CNN
1
. .
.
View
…
pooling
softmax
CNN
2
CNN : a second ConvNet
2
producing shape descriptors
Su et al. ICCV 2015

[Page contains 3 image(s)]


---
## Page 58
---


Experiments – Classification & Retrieval
Classification Retrieval
Method
(Accuracy) (mAP)
SPH 68.2% 33.3%
{
Non-deep
LFD 75.5% 40.9%
3D ShapeNets 77.3% 49.2%
FV, 12 views 84.8% 43.9%
CNN, 12 views 88.6% 62.8%
MVCNN, 12 views 89.9% 70.1%
MVCNN+metric, 12 views 89.5% 80.2%
MVCNN, 80 views 90.1% 70.4%
MVCNN+metric, 80 views 90.1% 79.5%
On ModelNet 40
Su et al. ICCV 2015

---
## Page 59
---


Multi-View Representations
•
Indeed gives good performance
•
Can leverage vast literature of image classification
•
Can use pretrained features
•
Need projection
•
What if the input is noisy and/or incomplete? e.g., point cloud
Slide Credit: Hao Su

---
## Page 60
---


Pixels -> Voxels
•
3D Conv Deep Belief Networks (CDBN)
Wu et al. CVPR 2015

[Page contains 2 image(s)]


---
## Page 61
---


Generative Modeling
Wu et al. CVPR 2015

[Page contains 2 image(s)]


---
## Page 62
---


3D-GANs
shape network
shape 3D shape
code
3D
Wu et al. NeurIPS 2016

[Page contains 6 image(s)]


---
## Page 63
---


Visual Object Networks (Geometry + Rendering)
differentiable projection
shape network texture network
depth
shape 3D shape 2D image
code
silhouette
viewpoint texture code
3D
2D
Wu et al. NeurIPS 2016 Zhu et al. NeurIPS 2018

[Page contains 14 image(s)]


---
## Page 64
---


Editing viewpoint, shape, and texture Interpolation in the latent space
viewpoint shape
shape texture
texture both
Transferring shape and texture
shape
viewpoint
image
shape
texture
Zhu et al. NeurIPS 2018

[Page contains 47 image(s)]


---
## Page 65
---


Octave Tree Representations
•
Store the sparse surface signals
•
Constrain the computation near the surface
Slide Credit: Hao Su

[Page contains 4 image(s)]


---
## Page 66
---


Octree: Recursively Partition the Space
Wang et al. O-CNN. SIGGRAPH 2017
Riegler et al. OctNet. CVPR 2017

[Page contains 3 image(s)]


---
## Page 67
---


Memory Efficiency
Memory (GB)
GPU Memory
6.
Voxel CNN O-CNN
4.5
3.
1.5
0.
16^3 32^3 64^3 128^3 256^3
O-CNN Resolution
Voxel CNN
Slide Credit: Hao Su

[Page contains 3 image(s)]


---
## Page 68
---


Octree Generating Networks
9
!(# )
Avoid reconstruction
•
Octree representation of shapes
•
Generate the octree layer by layer
Tatarchenko et al. ICCV 2017. Slide Credit: Hao Su

[Page contains 2 image(s)]


---
## Page 69
---


Points
Eulerian -> Lagrangian
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Eulerian -> Lagrangian
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 70
---


PPooiinnttNNeett:: FFiirrsstt LLeeaarrnniinngg TTooooll ffoorr PPooiinntt CClloouuddss
PointNet: Learning on Point Clouds
OObbjjeecctt CCllaassssiiffiiccaattiioonn
OObbjjeecctt PPaarrtt SSeeggmmeennttaattiioonn
PPooiinnttNNeett
SSeemmaannttiicc SScceennee PPaarrssiinngg
......
EEnndd--ttoo--eenndd lleeaarrnniinngg ffoorr iirrrreegguullaarr ppooiinntt ddaattaa
UUnniiffiieedd ffrraammeewwoorrkk ffoorr vvaarriioouuss ttaasskkss
CChhaarrlleess RR.. QQii,, HHaaoo SSuu,, KKaaiicchhuunn MMoo,, LLeeoonniiddaass JJ.. GGuuiibbaass..
PPooiinnttNNeett:: DDeeeepp LLeeaarrnniinngg oonn PPooiinntt SSeettss ffoorr 33DD
CCllaassssiiffiiccaattiioonn aanndd SSeeggmmeennttaattiioonn.. ((CCVVPPRR’’1177)) 1155
Slide credit: He Wang

[Page contains 1 table(s)]


### Table 1

|  | PPooiinnttNNeett:: FFiirrsstt LLeeaarrnniinngg TTooooll ffoorr PPooiinntt CClloouuddss
PointNet: Learning on Point Clouds |  |
| OObbjjeecctt CCllaassssiiffiiccaattiioonn
OObbjjeecctt PPaarrtt SSeeggmmeennttaattiioonn
PPooiinnttNNeett
SSeemmaannttiicc SScceennee PPaarrssiinngg
......
EEnndd--ttoo--eenndd lleeaarrnniinngg ffoorr iirrrreegguullaarr ppooiinntt ddaattaa
UUnniiffiieedd ffrraammeewwoorrkk ffoorr vvaarriioouuss ttaasskkss
CChhaarrlleess RR.. QQii,, HHaaoo SSuu,, KKaaiicchhuunn MMoo,, LLeeoonniiddaass JJ.. GGuuiibbaass..
PPooiinnttNNeett:: DDeeeepp LLeeaarrnniinngg oonn PPooiinntt SSeettss ffoorr 33DD
CCllaassssiiffiiccaattiioonn aanndd SSeeggmmeennttaattiioonn.. ((CCVVPPRR’’1177)) 1155
Slide credit: He Wang |  |  |
|  |  | 1155
Slide credit: He Wang |


[Page contains 2 image(s)]


---
## Page 71
---


IIInnnvvvaaarrriiiaaannnccceeesss
TThhee mmooddeell hhaass ttoo rreessppeecctt kkeeyy ddeessiiddeerraattaa ffoorr ppooiinntt cclloouuddss::
PPooiinntt PPeerrmmuuttaattiioonn IInnvvaarriiaannccee
PPooiinntt cclloouudd iiss aa sseett ooff uunnoorrddeerreedd ppooiinnttss
SSaammpplliinngg IInnvvaarriiaannccee
OOuuttppuutt aa ffuunnccttiioonn ooff tthhee uunnddeerrllyyiinngg ggeeoommeettrryy aanndd nnoott tthhee ssaammpplliinngg
Slide credit: He Wang
1166

[Page contains 1 table(s)]


### Table 1

|  |  |  |
|  | IIInnnvvvaaarrriiiaaannnccceeesss |  |
| TThhee mmooddeell hhaass ttoo rreessppeecctt kkeeyy ddeessiiddeerraattaa ffoorr ppooiinntt cclloouuddss::
PPooiinntt PPeerrmmuuttaattiioonn IInnvvaarriiaannccee
PPooiinntt cclloouudd iiss aa sseett ooff uunnoorrddeerreedd ppooiinnttss
SSaammpplliinngg IInnvvaarriiaannccee
OOuuttppuutt aa ffuunnccttiioonn ooff tthhee uunnddeerrllyyiinngg ggeeoommeettrryy aanndd nnoott tthhee ssaammpplliinngg
Slide credit: He Wang |  |  |
|  |  | Slide credit: He Wang |
| 1166 |  |  |


---
## Page 72
---


PPeerrmmuuttaattiioonn IInnvvaarriiaannccee:: SSyymmmmeettrriicc FFuunnccttiioonnss
Permutation Invariance: Symmetric Functions
EExxaammpplleess::
……
HHooww ccaann wwee ccoonnssttrruucctt aa uunniivveerrssaall ffaammiillyy ooff
ssyymmmmeettrriicc ffuunnccttiioonnss bbyy nneeuurraall nneettwwoorrkkss??
1177
Slide credit: He Wang

[Page contains 1 table(s)]


### Table 1

|  |  |  |
|  | PPeerrmmuuttaattiioonn IInnvvaarriiaannccee:: SSyymmmmeettrriicc FFuunnccttiioonnss
Permutation Invariance: Symmetric Functions |  |
| EExxaammpplleess::
……
HHooww ccaann wwee ccoonnssttrruucctt aa uunniivveerrssaall ffaammiillyy ooff
ssyymmmmeettrriicc ffuunnccttiioonnss bbyy nneeuurraall nneettwwoorrkkss??
1177
Slide credit: He Wang |  |  |
|  |  | 1177
Slide credit: He Wang |


[Page contains 4 image(s)]


---
## Page 73
---


Construct Symmetric Functions by Neural Networks
(1,2,3)
(1,1,1)
(2,3,2)
(2,3,4)
18
…
Construct Symmetric Functions by NNs
Simplest form: directly aggregate all points with a symmetric operator
Just discovers simple extreme/aggregate properties of the geometry.
=
(2,3,4)
Slide credit: He Wang

[Page contains 1 table(s)]


### Table 1

|  | Construct Symmetric Functions by Neural Networks
Construct Symmetric Functions by NNs |  |
|  | Simplest form: directly aggregate all points with a symmetric operator
Just discovers simple extreme/aggregate properties of the geometry.
(1,2,3)
(1,1,1)
=
(2,3,4)
(2,3,2)
…
(2,3,4)
18
Slide credit: He Wang |  |
|  |  | 18
Slide credit: He Wang |


[Page contains 3 image(s)]


---
## Page 74
---


Construct Symmetric Functions by Neural Networks
is symmetric if is symmetric
(1,2,3)
(1,1,1)
(2,3,2)
(2,3,4)
19
… …
Construct Symmetric Functions by NNs
PointNet
(vanilla)
Slide credit: He Wang

[Page contains 1 table(s)]


### Table 1

|  | Construct Symmetric Functions by Neural Networks
Construct Symmetric Functions by NNs |  |
|  | is symmetric if is symmetric
(1,2,3)
(1,1,1)
PointNet
(vanilla)
(2,3,2)
… …
(2,3,4)
19
Slide credit: He Wang |  |
|  |  | 19
Slide credit: He Wang |


[Page contains 5 image(s)]


---
## Page 75
---


Graph NNs on Point Clouds
•
Points -> Nodes
•
Neighborhood -> Edges
Convolution on Mesh/Graph
•
Graph NNs for point cloud processing
Message passing:
Wang et al. TOG 2019
Dynamic Graph CNN for Learning on Point Clouds,
ToG 2019
25

[Page contains 1 table(s)]


### Table 1

| Graph NNs on Point Clouds
•
Points -> Nodes
•
Neighborhood -> Edges
Convolution on Mesh/Graph
•
Graph NNs for point cloud processing
Message passing:
Wang et al. TOG 2019 |  |  |
|  | •
Neighborhood -> Edges
Convolution on Mesh/Graph
•
Graph NNs for point cloud processing |  |
|  | Message passing:
Wang et al. TOG 2019 |  |


[Page contains 2 image(s)]


---
## Page 76
---


DDDDiiiissssttttaaaannnncccceeee MMMMeeeettttrrrriiiiccccssss ffffoooorrrr PPPPooooiiiinnnntttt CCCClllloooouuuudddd
Distance Metrics for Point Clouds
AAAA PPPPooooiiiinnnntttt SSSSeeeetttt GGGGeeeennnneeeerrrraaaattttiiiioooonnnn NNNNeeeettttwwwwoooorrrrkkkk ffffoooorrrr 3333DDDD OOOObbbbjjjjeeeecccctttt
RRRReeeeccccoooonnnnssssttttrrrruuuuccccttttiiiioooonnnn ffffrrrroooommmm aaaa SSSSiiiinnnngggglllleeee IIIImmmmaaaaggggeeee,,,, CCCCVVVVPPPPRRRR 2222000011116666
22222222
Slide credit: He Wang

[Page contains 1 table(s)]


### Table 1

|  |  |  |
|  | DDDDiiiissssttttaaaannnncccceeee MMMMeeeettttrrrriiiiccccssss ffffoooorrrr PPPPooooiiiinnnntttt CCCClllloooouuuudddd
Distance Metrics for Point Clouds |  |
| AAAA PPPPooooiiiinnnntttt SSSSeeeetttt GGGGeeeennnneeeerrrraaaattttiiiioooonnnn NNNNeeeettttwwwwoooorrrrkkkk ffffoooorrrr 3333DDDD OOOObbbbjjjjeeeecccctttt
RRRReeeeccccoooonnnnssssttttrrrruuuuccccttttiiiioooonnnn ffffrrrroooommmm aaaa SSSSiiiinnnngggglllleeee IIIImmmmaaaaggggeeee,,,, CCCCVVVVPPPPRRRR 2222000011116666
22222222
Slide credit: He Wang |  |  |
|  |  | 22222222
Slide credit: He Wang |


[Page contains 20 image(s)]


---
## Page 77
---


Points
Non-Parametric -> Parametric
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Non-Parametric -> Parametric
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 78
---


PPaarraammeettrriiccDDeeccooddeerr::AAttllaassNNeett
Parametric Decoder: AtlasNet
Parametric Decoder: AtlasNet
GGiviveenn t thhee o ouuttppuutt p pooininttss f foorrmm a a s smmooootthh s suurrffaaccee, ,e ennffoorrccee s suucchh a a
ppaarraammeettrrizizaattioionn i nin i ninppuutt..
Given the output points form a smooth surface,
enforce such a parametrization as inpMuMt.LLPP(([[zz, ,u uvv]])) - ->> p pooinintt
MLP(", $, %) -> point
AAlslsoo, ,y yoouu c caann g geett M Meesshh!!
AAtltalassNNeet:t :A A P Paappieier-rM-MaacchhˆˆeeAApppproroaacchh t oto L Leeaarnrniningg 3 3DD S Suurfrafaccee
3838
GGeenneeraratitoionn, , C CVVPPRR 2 2001188 Groueix et al. CVPR 2018
One parameterization is limited for objects with complex
topology.
So, more sheets.
AtlasNet: A Papier-Machˆe Approach to Learning 3D Surface
Generation, CVPR 2018
39

[Page contains 1 table(s)]


### Table 1

|  |  | PPaarraammeettrriiccDDeeccooddeerr::AAttllaassNNeett |  |  |  |  |  |  |
|  |  | Parametric Decoder: AtlasNet
Parametric Decoder: AtlasNet
GGiviveenn t thhee o ouuttppuutt p pooininttss f foorrmm a a s smmooootthh s suurrffaaccee, ,e ennffoorrccee s suucchh a a
ppaarraammeettrrizizaattioionn i nin i ninppuutt..
Given the output points form a smooth surface,
enforce such a parametrization as inpMuMt.LLPP(([[zz, ,u uvv]])) - ->> p pooinintt
MLP(", $, %) -> point
AAlslsoo, ,y yoouu c caann g geett M Meesshh!!
AAtltalassNNeet:t :A A P Paappieier-rM-MaacchhˆˆeeAApppproroaacchh t oto L Leeaarnrniningg 3 3DD S Suurfrafaccee
3838
GGeenneeraratitoionn, , C CVVPPRR 2 2001188 Groueix et al. CVPR 2018 |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  | Parametric Decoder: A | tlasNet |  |  |  |  |
|  |  |  | GGiviveenn t thhee o ouuttppuutt p pooininttss f foorrmm a a s smmooootthh s suurrffaaccee, ,e ennffoorrccee s suucchh a a
ppaarraammeettrrizizaattioionn i nin i ninppuutt..
Given the output points form a smooth surface,
enforce such a parametrization as inpMuMt.LLPP(([[zz, ,u uvv]])) - ->> p pooinintt
MLP(", $, %) -> point
AAlslsoo, ,y yoouu c caann g geett M Meesshh!!
AAtltalassNNeet:t :A A P Paappieier-rM-MaacchhˆˆeeAApppproroaacchh t oto L Leeaarnrniningg 3 3DD S Suurfrafaccee
3838
GGeenneeraratitoionn, , C CVVPPRR 2 2001188 Groueix et al. CVPR 2018 |  |  |  |  |  |
|  |  |  |  |  | 3838
Groueix et al. CVPR 2018 |  |  |  |


[Page contains 7 image(s)]


---
## Page 79
---


Comparison
Results
Input image Point cloud
Voxel AtlasNet
AtlasNet: A Papier-Machˆe Approach to Learning 3D Surface
Generation, CVPR 2018
Groueix et al. CVPR 2018
40

[Page contains 1 table(s)]


### Table 1

|  |  |  |
|  | Comparison |  |
|  | Results
Input image Point cloud
Voxel AtlasNet
AtlasNet: A Papier-Machˆe Approach to Learning 3D Surface
Generation, CVPR 2018
Groueix et al. CVPR 2018
40 |  |
|  |  | Groueix et al. CVPR 2018
40 |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 80
---


Points
Explicit -> Implicit
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Explicit -> Implicit
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 81
---


Deep Implicit Functions
Liu et al. Learning to Infer Implicit Surfaces without 3D Supervision. NeurIPS 2019
Deep Level Sets: Implicit Surface Representations for 3D Shape Inference. 2019 DeepSDF. CVPR 2019

[Page contains 3 image(s)]


---
## Page 82
---


Chen and Zhang.
Occupancy Networks Learning Implicit Fields
CVPR 2019
CVPR 2019
Liu et al. Learning to Infer Implicit Surfaces without 3D Supervision. NeurIPS 2019
Deep Level Sets: Implicit Surface Representations for 3D Shape Inference. 2019 DeepSDF. CVPR 2019

[Page contains 5 image(s)]


---
## Page 83
---


Collection of Implicit Functions
Genova et al. CVPR 2020

[Page contains 1 image(s)]


---
## Page 84
---


Implicit Functions for Geometry + Rendering
NeRF. Mildenhall*, Srinivasan*, et al. ECCV 2020

[Page contains 3 image(s)]


---
## Page 85
---


Volume rendering is trivially differentiable.
Rendering model for ray :(;) = < + ;=:
Ray
$ !, #
differentiable w.r.t.
! ≈ ∑ $ % !
! ! !
'
!"# ;"#!
"
)
colors $
weights
'
$
3D volume
How much light is blocked earlier along ray:
'
'! (
! $
!&#
$ = ∏ (1 − % )
! %
%"#
Camera
! "
How much light is contributed by ray segment :
!
Slide credit: Ben Mildenhall

[Page contains 9 image(s)]


---
## Page 86
---


Reconstruction & Novel View Synthesis with NeRF
Mildenhall*, Srinivasan*, et al. ECCV 2020

[Page contains 2 image(s)]


---
## Page 87
---


Generative Modeling with Implicit Geometry + Rendering
differentiable projection
shape network texture network
depth
shape 3D shape 2D image
code
silhouette
viewpoint texture code
Wu et al. NeurIPS 2016 Zhu et al. NeurIPS 2018

[Page contains 4 image(s)]


---
## Page 88
---


Generative Modeling with Implicit Geometry + Rendering
shape network 3D density & radiance field
shape
code
Kerbl*

[Page contains 17 image(s)]


---
## Page 89
---


Points
Explicit <-> Implicit
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Explicit <-> Implicit
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 90
---


NeRF parameterizes scenes densely, at every point in space.
Slide credit: Vincent Sitzmann

[Page contains 3 image(s)]


---
## Page 91
---


Gaussian splatting parameterizes the scene sparsely, only
where density is nonzero.
3D Gaussian blobs
(extended points)
floating in space
= 1
RGB =
σ
= 0.5
= 0
RGB =
σ
σ
Slide credit: Vincent Sitzmann

[Page contains 3 image(s)]


---
## Page 92
---


Reconstruction Using 3DGS
Kerbl et al. ACM TOG (SIGGRAPH) 2023

[Page contains 2 image(s)]


---
## Page 93
---


Quality & Efficiency
Kerbl et al. ACM TOG (SIGGRAPH) 2023

[Page contains 2 image(s)]


---
## Page 94
---


Points
Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex shapes?
CS184/284A Ren Ng

[Page contains 1 table(s)]


### Table 1

| Shape Representations
Explicit Implicit
Non-parametric
Algebraic Surfaces (Implicit)
Points Meshes Voxels Level Sets
Surface is zero set of a polynomial in x, y, z
Parametric
Splines Subdivision Algebraic Constructive
Surfaces Surfaces Solid Geometry
More complex s |  |
|  | Algebraic Surfaces (Implicit)
Voxels Level Sets
Surface is zero set of a polynomial in x, y, z |
|  | Algebraic Constructive
Surfaces Solid Geometry
More complex s |


[Page contains 14 image(s)]


---
## Page 95
---


Anatomy of a Structure-Aware Representation
Element Structure Element Geometry
Slide credit: Daniel Ritchie

[Page contains 2 image(s)]


---
## Page 96
---


Anatomy of a Structure-Aware Representation
Element Structure Element Geometry
Slide credit: Daniel Ritchie

[Page contains 2 image(s)]


---
## Page 97
---


Representing Element Structure
•
Segmented Geometry
• Simple to construct
• Re-use models for unstructured geometry
• Integrity of atomic elements not guaranteed
by construction (generative model must learn
to output coherent segments)
[WSH∗18]
[WSCR18]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]


---
## Page 98
---


Representing Element Structure
•
Segmented Geometry
•
Part Sets
• Part integrity guaranteed
• No relationships between parts (e.g. nothing
to prevent parts from “floating”)
[SSK∗17]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]


---
## Page 99
---


Sets of Volumetric Primitives
Tulsiani et al. CVPR 2017

[Page contains 2 image(s)]


---
## Page 100
---


Sets of Implicit Functions
Genova et al. CVPR 2020

[Page contains 1 image(s)]


---
## Page 101
---


Representing Element Structure
•
Segmented Geometry
•
Part Sets
•
Relationship Graphs
• Can enforce important relationships (e.g.
connectivity)
• In general, machine learning models for graph
generation still an open problem
[WLW∗19]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]


---
## Page 102
---


Representing Element Structure
•
Segmented Geometry
•
Part Sets
•
Relationship Graphs
•
Hierarchies
• Tree generative models better understood
than graph generative models
• Not all structures of interest can be (naturally)
expressed as trees
[WXL∗11]
[LPX*10]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]


---
## Page 103
---


Representing Element Structure
•
Segmented Geometry
•
Part Sets
•
Relationship Graphs
•
Hierarchies
•
Hierarchical Graphs
• Models both naturally hierarchical structure as
well as naturally lateral relationships
• Graphs per level are simpler à easier to
generate than large, general-purpose graphs
• Difficult to obtain / expensive to annotate
data in this format
[MGY*19a]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]


---
## Page 104
---


Hierarchical Graph of Shape Primitives
Graph convnets
encode/decode
variable-degree
nodes
StructureNet. Mo et al. 2019

[Page contains 2 image(s)]


---
## Page 105
---


Representing Element Structure
•
Segmented Geometry
•
Part Sets
•
Relationship Graphs
•
Hierarchies
•
Hierarchical Graphs
•
Programs • Subsumes all other representations (programs
can generate any of them)
• Express natural degrees of freedom via free
parameters
• Even more difficult to get data in this format
[ERSLT18]
[TLS*19]
Slide credit: Daniel Ritchie

[Page contains 1 image(s)]
