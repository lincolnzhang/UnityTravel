#UnityTravel
===========

start unity travel to game world

## How to save cache by PlayerPrefs


**Description**

Stores and accesses player preferences between game sessions.

**Maximum Number**

There is no limit with number of PlayerPrefs in ANY platforms. But there is a limit of 1 MB in Web player build. 

Other than that there aint any limit with number of or size of PlayerPrefs.

Generally PlayerPrefs are a bit slow (esp while saving it!) So i always prefer handling it in Start() and OnApplicationQuit() functions. 

And never prefer to save it in Update or OnGUI or any other function that gets called every frame.

And if it is array go with ArrayPrefs2, that would be better!. IDK about change in performance with number of prefs.

And even if there is any i dont think it would be some huge impact. 

Because in one of my games, i have handled over 300 mb of playerprefs and i didnt find a difference, it was for iOS and android.

**Sample Code**

<pre><code>   private var save1:String = “”; 
	
　　private var read1:String = “”;
	
　　function OnGUI (){
	
　　save1 = GUILayout.TextField (save1, GUILayout.Width (200));
	
　　if (GUILayout.Button (“Save”)) {
	
　　PlayerPrefs.SetString (“save1”, save1);//设定“save1”空间，并存入save1变数的字串资料
	
　　PlayerPrefs.Save ();//存档
	
　　}
	
　　if (GUILayout.Button (“Read”)) {
	
　　read1 = PlayerPrefs.GetString (“save1”);//把“save1”空间的资料取出，存入read1变数里
	
　　}
	
　　GUILayout.Label (read1);
	
　　if (GUILayout.Button (“Delete key”)) {

　　PlayerPrefs.DeleteKey (“save1”);//删除“save1”空间的资料
	
　　}
	
　　if (GUILayout.Button (“Delete all keys”)) {
	
　　PlayerPrefs.DeleteAll ();//删除所有存档
	
　　}
	
　　}</code></pre>
