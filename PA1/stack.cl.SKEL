(*
 *  CS164 Fall 94
 *
 *  Programming Assignment 1
 *    Implementation of a simple stack machine.
 *
 *  Skeleton file
 *)

class StackItem {
  item : String;
  next : StackItem;
  getItem() : String {
  	    item
  };
  putItem(a: String):String {
     {
  	     item <- a;
	     a;
     }
  };
  getNext() : StackItem {
  	    next
  };
  putNext(a: StackItem) : StackItem {
    {
  	    next <- a;
	    next;
    }
  };
};

class Stack inherits IO {
  size: Int;
  maxSize: Int;
  itemPnt: StackItem;
  (* method to init the stack *)
  init(maxS: Int) : Stack {
    {
	size <- 0;
	maxSize <- maxS;
	self;
    }
  };

  (* method to pop, if none then return a void item *)
  pop() : String {
    {
	let res:String in 
	{
	if (size = 0) then 
	    res
	else
	    {
	    res <- itemPnt.getItem();
	    itemPnt <- itemPnt.getNext();
	    size <- size - 1;
	    res;
	    }
	fi;
	};
    }
  };

  (* method to push, input is a string *)
  push(a: String) : Bool {
      {
	if (size = (maxSize)) then
	    false
	else
	    {
		let newItem:StackItem <- new StackItem in
		    {
		      		newItem.putItem(a);
				size <- size + 1;
				newItem.putNext (itemPnt);
				itemPnt <- newItem;
				true;
		    };
	    } 
	fi;
    }
  };

  isEmpty() : Bool {
	if (size = 0) then
		true
	else
		false
	fi
  };

  printStack() : String {
	(* print to a string from the mostrecent to last *)
    {
	let res : String  in 
	{
	if (size = 0) then
	    res
	else
	    {
		let tmpIter : StackItem <- itemPnt in 
		{
		
		while (not (isvoid tmpIter))  loop	
		    {
			res <- res.concat(" + ");
			res <- res.concat(tmpIter.getItem());
			tmpIter <- tmpIter.getNext();
		    }					
		pool;
		res;
		};
	    }
	    fi;
	 }; 
    }
  };
};

class Main inherits IO {

   main() : Object {
    {
        out_string("self test\n");
	let s : Stack <- (new Stack).init(3) in 
	{
	s.push("a");
	s.push("b");
	s.push("c");
	out_string("test for pop \n");
	out_string(s.pop().concat("\n"));	
	out_string(s.printStack().concat("\n"));
	out_string("end of 1st test\n");
	out_string("test the max size of stack\n");
	s.push("df");
	s.push("extra");
	out_string(s.printStack().concat("\n"));
	s;
	};
    }
   };

};
