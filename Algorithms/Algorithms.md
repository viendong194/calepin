See also [Math](../Math/Math.md)

## Resources

- [List of algorithms — Wikipedia](https://en.wikipedia.org/wiki/List_of_algorithms)
- [FAQ mathématiques pour les jeux](https://jeux.developpez.com/faq/math/)
- [FAQ Programmation 3D](https://jeux.developpez.com/faq/3d/)
- [Gamasutra - Features: Programming](http://www.gamasutra.com/features/programming/)
- [GPU Gems 3 - Foreword](http://http.developer.nvidia.com/GPUGems3/gpugems3_pref01.html)
- [Principles Of HTML5 Game Design](https://www.smashingmagazine.com/2015/09/principles-of-html5-game-design/)
- [Articles - Articles - GameDev.net](https://www.gamedev.net/resources)
- [Amit’s Game Programming Information](http://www-cs-students.stanford.edu/~amitp/gameprog.html)
- [jj's useful and ugly FXT page](http://www.jjj.de/fxt/fxtpage.html#fxt)
- [Essential Math for Games Programmers](http://www.essentialmath.com/tutorial.htm)
- [Collection of projects and links about algorithm visualization](https://github.com/enjalot/algovis)
- [Algorithm Visualizer](http://algo-visualizer.jasonpark.me/) - Algorithm Visualizer. see <https://github.com/parkjs814/AlgorithmVisualizer>
- [The Stony Brook Algorithm Repository](http://www8.cs.umu.se/kurser/TDBAfl/VT06/algorithms/WEBSITE/INDEX.HTM) - Algorithms and implementations
- [The pocket handbook of image processing algorithms in C](http://adaptiveart.eecs.umich.edu/2011/wp-content/uploads/2011/09/The-pocket-handbook-of-image-processing-algorithms-in-C.pdf)
- [Javascript Math Toolkit](https://github.com/theAlgorithmist/JSMathToolkit) - math library
- [Rosetta Code](http://rosettacode.org/wiki/Rosetta_Code)
- [Algorithms | Computer science | Computing | Khan Academy](https://www.khanacademy.org/computing/computer-science/algorithms)
- [NASA's Software Catalog](https://software.nasa.gov/)
- [Algorithms \[Algorithm Wiki\]](http://will.thimbleby.net/algorithms/doku.php)
- [sherxon/AlgoDS: Implementation of Algorithms and Data Structures, Interview Questions and Answers](https://github.com/sherxon/AlgoDS/)
- [10 Common Data Structures Explained with Videos + Exercises](https://medium.freecodecamp.org/10-common-data-structures-explained-with-videos-exercises-aaff6c06fb2b)

## GPU computing

> GPU can do lot of pallel work, but the latency involved in getting results back from the GPU make this unattractive for realtime

See also SMID

- [Computing with WebGL](../Development/JavaScript/JavaScript.md#computing-with-webgl)
- [Marching cubes](./Marching%20cubes/Marching%20cubes.md)
- [GPU physics](../Math/Physics/Physics.md#gpu-physics)
- [Tree traversal](./Tree%20traversal/Tree%20traversal.md)
- [Condition optimizations](../Graphics/Graphics.md#condition-optimizations)
- [Binary search](#binary-search)

## Progressive data

PNG use Adam7 algorithm:

```
1 6 4 6 2 6 4 6
7 7 7 7 7 7 7 7
5 6 5 6 5 6 5 6
7 7 7 7 7 7 7 7
3 6 4 6 3 6 4 6
7 7 7 7 7 7 7 7
5 6 5 6 5 6 5 6
7 7 7 7 7 7 7 7
```

```c
//Progressive PNG
/*
	variables declared and initialized elsewhere in the code:
		height, width
	functions or macros defined elsewhere in the code:
		visit(), min()
 */
 
int starting_row[7]  = { 0, 0, 4, 0, 2, 0, 1 };
int starting_col[7]  = { 0, 4, 0, 2, 0, 1, 0 };
int row_increment[7] = { 8, 8, 8, 4, 4, 2, 2 };
int col_increment[7] = { 8, 8, 4, 4, 2, 2, 1 };
int block_height[7]  = { 8, 8, 4, 4, 2, 2, 1 };
int block_width[7]   = { 8, 4, 4, 2, 2, 1, 1 };

int pass;
long row, col;

pass = 0;
while (pass < 7)
{
	row = starting_row[pass];
	while (row < height)
	{
		col = starting_col[pass];
		while (col < width)
		{
			visit(row, col,
				  min(block_height[pass], height - row),
				  min(block_width[pass], width - col));
			col = col + col_increment[pass];
		}
		row = row + row_increment[pass];
	}
	pass = pass + 1;
}
```

![An illustration of Adam7 interlacing over a 16×16 image](https://upload.wikimedia.org/wikipedia/commons/2/27/Adam7_passes.gif)
![adam7gif.gif](http://www.libpng.org/pub/png/img_png/adam7gif.gif)

- [Adam7 algorithm — Wikipedia](https://en.wikipedia.org/wiki/Adam7_algorithm)
- [PNG Adam7 interlacing](http://www.schaik.com/png/adam7.html)
- <http://www.w3.org/TR/PNG/#8Interlace>
- <http://www.w3.org/TR/PNG/#4Concepts.Encoding>
- <http://www.w3.org/TR/PNG/#13Progressive-display>

## Algorithm/math formula in scientific papier

- [How to implement an algorithm from a scientific paper | Code Capsule](http://codecapsule.com/2012/01/18/how-to-implement-a-paper/)
- [a cheat-sheet for mathematical notation in code form](https://github.com/Jam3/math-as-code)
- [A paper algorithm notation](http://canonical.org/~kragen/sw/dev3/paperalgo)
- [How to Read a Paper](http://blizzard.cs.uwaterloo.ca/keshav/home/Papers/data/07/paper-reading.pdf)

## Language detection

- [LanguageIdentifier (Apache Tika 1.5 API)](https://tika.apache.org/1.5/api/org/apache/tika/language/LanguageIdentifier.html)

## Hash

```c
// Knuth multiplicative hash where unsigned integer overflow is used to perform the moduolo operation
uint32_t hash(uint32_t v)
{
	return v * UINT32_C(2654435761);
}
```

- [c++ - knuth multiplicative hash - Stack Overflow](https://stackoverflow.com/questions/11871245/knuth-multiplicative-hash)
- [Hash table — Wikipedia](https://en.wikipedia.org/wiki/Hash_table#Choosing_a_good_hash_function) - Choosing a good hash function

## Inverse kinematics

- [Inverse kinematics — Wikipedia](https://en.wikipedia.org/wiki/Inverse_kinematics)
- [Simple Two Joint IK](http://theorangeduck.com/page/simple-two-joint) - A simple intuitive method for two joint IK

## Tree

- [R-tree — Wikipedia](https://en.wikipedia.org/wiki/R-tree)
- [Tree Traversal in C without Recursion | Dr Dobb's](http://www.drdobbs.com/tree-traversal-in-c-without-recursion/184401260)
	
	```c
	void tree_depth_traversal1 (struct t_node *root, void (*process)(struct t_node *node, int first_flag))
	{
		// TRUE  1st exploration of node,  continue with 1st subnode
		// FALSE node completely explored, continue with sibling
		int dir_flag = TRUE;
		
		// the current node during exploration
		struct t_node *current = root;
		
		//----- no tree or no user function , nothing to do
		if ((root == NULL) || (process == NULL)) return;
		
		//----- the root pre order
		(* process) (root, TRUE);
		
		if (has_sub(root))
		{
			//----- the exploration loop
			current = get_sub(root);
			while (node_exist(current)
				&& ((current != root) || (dir_flag == TRUE)))
			{
				//--- process the node : TRUE prefix, FALSE postfix
				
				(* process) (current, dir_flag);
				
				//--- 1st expl. of the node, continue with 1st subnode
				// or stay for 2nd part of the process
				if (dir_flag == TRUE)
				{
					if (has_sub(current))
						current = get_sub(current);
					else
					// 1st exploration of current node is finished
					// go to 2nd exploration of the current node
					dir_flag = FALSE;
				}
				
				//--- second expl. of the node, continue with sibling
				// or the parent if no sibling
				else
				{
					if (has_sibling(current))
					{
						// goto 1st exploration of the sibling 
						// (now current)
						current = get_sibling(current);
						
						dir_flag = TRUE;
					}
					else
						current = get_parent(current);
				}
			}
			// ASSERT ((current == root) && (dir_flag == FALSE));
		}
		
		//----- the root post order
		(* process) (root, FALSE);
	}
	```

## Fast Inverse Square Root

Aka Quake Fast Inverse Square Root

**Note: be carefull about speed. The ECMAScript version is useless compared to the speed of `1 / Math.sqrt(x)`.**

```c
// From https://stackoverflow.com/questions/11644441/fast-inverse-square-root-on-x64/41637260#41637260 Fast Inverse Square Root on x64
#include <cstdint>

// Fast inverse square root double version (64 bit floating point)
double rsqrt( double number )
{
	std::int64_t i;
	double x2, y;
	const double threehalfs = 1.5;
	
	x2 = number * 0.5;
	y = number;
	i = *(std::int64_t *) &y;// evil floating point bit level hacking
	i = 0x5fe6eb50c7b537a9 - (i >> 1);// what the fuck? 
	y = *(double *) &i;
	y = y * ( threehalfs - ( x2 * y * y ) );// 1st iteration
//	y = y * ( threehalfs - ( x2 * y * y ) );// 2nd iteration, this can be removed
	return y;
}
```

For the code before, note:

> you also have SSE (especially on x64) and its own inverse square root (intrinsic: `_mm_rsqrt_ss/ps`) is probably faster and more precise than Carmack's hack. Of course it still only works for 32-bit floats, but **you don't use doubles for inaccurate approximate values anyway**
> — [Christian Rau](https://stackoverflow.com/questions/11644441/fast-inverse-square-root-on-x64#comment15427042_11644441)

```js
// ~2x quicker than 1/Math.sqrt(x)
// Be carefull of byte order! DataView is ~20x slower
const buffer = new ArrayBuffer(Float32Array.BYTES_PER_ELEMENT);
const fv = new Float32Array(buffer);
const lv = new Uint32Array(buffer);
const threehalfs = 1.5;

function rsqrt(number) {
	let x2 = number * 0.5;
	// evil floating point bit level hacking by using float and uint views for the same buffer
	fv[0] = number;
	lv[0] = 0x5f3759df - ( lv[0] >> 1 );// what the fuck?
	let y = fv[0];
	y = y * ( threehalfs - ( x2 * y * y ) );// 1st iteration
//	y = y * ( threehalfs - ( x2 * y * y ) );// 2nd iteration, this can be removed
	return y;
}
```

- [Fast inverse square root — Wikipedia](https://en.wikipedia.org/wiki/Fast_inverse_square_root)
- [Understanding Quake’s Fast Inverse Square Root – BetterExplained](https://betterexplained.com/articles/understanding-quakes-fast-inverse-square-root/)
- [math - Why is fast inverse square root so odd and slow on Java? - Stack Overflow](https://stackoverflow.com/questions/16551140/why-is-fast-inverse-square-root-so-odd-and-slow-on-java)
- [floating point - How to implement the "fast inverse square root" in Java? - Stack Overflow](https://stackoverflow.com/questions/11513344/how-to-implement-the-fast-inverse-square-root-in-java)
- [Implement Fast Inverse Square Root in Javascript? - Game Development Stack Exchange](http://gamedev.stackexchange.com/questions/30727/implement-fast-inverse-square-root-in-javascript)

## Nearest neighbor search

See also [binary search](#binary-search)

See [Nearest neighbor search — Wikipedia](https://en.wikipedia.org/wiki/Nearest_neighbor_search)

## Binary search

See also [nearest neighbor search](#nearest-neighbor-search)

```js
// From http://wayback.archive.org/web/20131006181606/http://www.brooksandrus.com/blog/2008/11/12/improve-flash-mpeg-4-avc-seeking-with-binary-search/#comment-49096 Improve Flash MPEG-4 AVC Seeking With Binary Search | Brooks Andrus
/**
* Loops through an array of seekpoints to find a requested time. 
* If the value is found within the array of seekpoints the index at which 
* the value is found is returned. If an exact match is not found, -1 is returned 
* and the the upper and lower indices between which the value falls are set 
* (so you can determine the closest indice, or seek to to the nearest indexed 
* time behind or forward in the array of seekpoints.
* 
* Seekpoints array must be sorted.
* 
* @param {number} value	the requested seek time to find
* @param {Array} range the array of seekpoints collected from an MPEG-4 AVC NetStream metadata event
* @param {number} the low index within the range we'd like to scan
* @param {number} the high index within the range we'd like to scan
* 
*/
function binarySearch(value, range, low, high)
{
	var val = -1;
	var time;
	while (low < = time	)
	{
		var median = (low + high) / 2;
		time = range[median].time;
		if (value > time	)
		{
			low = median + 1;
		}
		else if (value < time	)
		{
			high = median - 1;
		}
		else // found a match
		{
			low = median;
			high = median;
			val = median;
			break;
		}
	}
	_upperBounds = low;
	_lowerBounds = high;
	return val; // failed to find value. Look at the upper / lower bounds
}

// binarySearch( 33.3, [0,10,20,30,40,50], 0, 6 ) returns 3
// binarySearch( 30.0, [0,10,20,30,40,50], 0, 6 ) returns 3
// binarySearch( 90  , [0,10,20,30,40,50], 0, 6 ) returns 5
// binarySearch( 0   , [0,10,20,30,40,50], 0, 6 ) returns 0
// binarySearch( -90 , [0,10,20,30,40,50], 0, 6 ) returns -1
```

- [Implementing binary search of an array (article) | Khan Academy](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/implementing-binary-search-of-an-array)
- [SIMD / GPU Friendly Branchless Binary Search « The blog at the bottom of the sea](https://blog.demofox.org/2017/06/20/simd-gpu-friendly-branchless-binary-search/)

## LZ77

- [lecture07.pdf](https://www.cs.helsinki.fi/u/tpkarkka/opetus/12k/dct/lecture07.pdf)

## Hash table

- [Hash table — Wikipedia](https://en.wikipedia.org/wiki/Hash_table)
- [A very fast hashtable ](https://github.com/skarupke/flat_hash_map) - see [I Wrote The Fastest Hashtable | Probably Dance](https://probablydance.com/2017/02/26/i-wrote-the-fastest-hashtable/)

## Constraint solver

- <https://github.com/slightlyoff/cassowary.js>
- [UW Cassowary Constraint Solving Toolkit](http://constraints.cs.washington.edu/cassowary/)
- [Quadrilateral demo - Cassowary Javascript](http://www.badros.com/greg/cassowary/js/quaddemo.html) - <http://www.badros.com/greg/cassowary/js/quaddemo.js>
- <http://cassowary.cvs.sourceforge.net/viewvc/cassowary/cassowary/js/> 

## Diamond-square

- [Diamond-square algorithm — Wikipedia](https://en.wikipedia.org/wiki/Diamond-square_algorithm)
- [labs.hellokeita.com » Multi Gradient](http://wayback.archive.org/web/20120225094220/http://labs.hellokeita.com/2008/01/24/multi-gradient/)

1. get the top left and bottom left corner colors of the square
2. get the half height of the edge and also the average color of those colors.
3. repeat that until you have all pixels of the edge.
4. you make the same with the right edge.
5. do it for each edge from the top to bottom.

If you work around more, you can create gradient spots from any pixel you wish easily.

## Luhn

- [Luhn algorithm — Wikipedia](https://en.wikipedia.org/wiki/Luhn_algorithm)

Could be simplier that example below:

```js
// http://jqueryvalidation.org/creditcard-method/
function test( value ) {
	// accept only spaces, digits and dashes
	if ( /[^0-9 \-]+/.test( value ) ) {
		return false;
	}
	var nCheck = 0,
		nDigit = 0,
		bEven = false,
		n, cDigit;
	
	value = value.replace( /\D/g, "" );
	
	// Basing min and max length on
	// http://developer.ean.com/general_info/Valid_Credit_Card_Types
	if ( value.length < 13 || value.length > 19 ) {
		return false;
	}
	
	for ( n = value.length - 1; n >= 0; n--) {
		cDigit = value.charAt( n );
		nDigit = parseInt( cDigit, 10 );
		if ( bEven ) {
			if ( ( nDigit *= 2 ) > 9 ) {
				nDigit -= 9;
			}
		}
		nCheck += nDigit;
		bEven = !bEven;
	}
	
	return ( nCheck % 10 ) === 0;
}
```

```js
// Luhn algorithm validator, by Avraham Plotnitzky. (aviplot at gmail)
function luhnCheckFast(luhn)
{
	var ca, sum = 0, mul = 0;
	var len = luhn.length;
	while (len--)
	{
		ca = parseInt(luhn.charAt(len),10) << mul;
		sum += ca - (ca>9)*9; // sum += ca - (-(ca>9))|9
		// 1 <--> 0 toggle.
		mul ^= 1; // mul = 1 - mul;
	};
	return (sum%10 === 0) && (sum > 0);
}
```

```js
// https://gist.github.com/2134376
// Phil Green (ShirtlessKirk)
const prodArr = [[0, 1, 2, 3, 4, 5, 6, 7, 8, 9], [0, 2, 4, 6, 8, 1, 3, 5, 7, 9]];
function luhnChk(luhn) {
	let length = luhn.length,
	let mul = 0;
	let sum = 0;
	
	while (length--) {
		sum += prodArr[mul][parseInt(luhn.charAt(length), 10)];
		mul ^= 1;
	}
	
	return sum % 10 === 0 && sum > 0;
}
```
