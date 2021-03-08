		 		if (this.ts != null)
		 		{
		 			return this.ts == v.ts; //FIXME:???
		 		}
---------------------
TODO:

growvector
new()
newvector

using lua_Object = System.UInt32;
sizeof()

------------------
long ??? Long

--->	using Long = System.Int32;
	
	public partial class Lua
	{
		public class YYSTYPE //FIXME:union
		{
		。。。
--->			 private long  vLong_;
			 

-------------------
if ( yy_ps >= new IntegerPtr(yys, (int)yymaxdepth) )	/* room on stack? */
->
mod to minus compare

------------------
malloc
memcpy
newvector

---------------------
GetHashCode

----------------------
数组改变导致无法做加减和算数比较运算

//basepc = growvector(basepc, maxcurr, Byte);
Byte[] oldarr = basepc.chars;
basepc = new BytePtr(new Byte[maxcurr], 0);


-------------------

/*
		public class NodeRef
		{
			public int index = -1;
			public NodeRef(int index)
			{
				this.index = index;
			}
			
			public static NodeRef assign(Node node)
			{
				if (node == null)
				{
					return null;
				}
				else
				{
					return new NodeRef(node.index);
				}
			}
			
			public static NodeRef assign(NodeRef node)
			{
				if (node == null)
				{
					return null;
				}
				else
				{
					return new NodeRef(node.index);
				}
			}
			
			public Node get()
			{
				if (index < 0)
				{
					return null;
				}
				else
				{
					return Node.global_nodes[index];
				}
			}
			
			public Node get(int idx)
			{
				if (index + idx < 0)
				{
					return null;
				}
				else
				{
					return Node.global_nodes[index + idx];
				}
			}
		}
		*/
		
-----------------------
see _malloc_str


		public class StringNode {
			public StringNode next;
			public TaggedString ts = new TaggedString();
			public CharPtr _malloc_str;
			public StringNode(char[] malloc_str)
			{
				this._malloc_str = new CharPtr(malloc_str);
			}
		}
		
		
		public class TreeNode
		{
		 	public TreeNode right;
		 	public TreeNode left;
		 	public ushort varindex;  /* != NOT_USED  if this is a symbol */
		 	public ushort constindex;  /* != NOT_USED  if this is a constant */
		 	public TaggedString ts = new TaggedString();
		 	public CharPtr _malloc_str = null;
		 	
		 	public TreeNode(char[] malloc_str)
		 	{
		 		this._malloc_str = new CharPtr(malloc_str);
		 	}
		}
		
		
TODO: luaI_malloc
luaI_free
luaI_realloc
//#define new(s)          ((s *)luaI_malloc(sizeof(s)))
//#define newvector(n,s)  ((s *)luaI_malloc((n)*sizeof(s)))
//#define growvector(old,n,s) ((s *)luaI_realloc(old,(n)*sizeof(s)))
------------------------



		
		