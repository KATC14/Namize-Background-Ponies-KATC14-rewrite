// ==UserScript==
// @name         Namize Background Ponies! (KATC14 rewrite)
// @description  Namize Background Ponies on Derpibooru!
// @icon         https://u.smutty.horse/mbzdgrpesio.png
// @include      http*://*derpibooru.org/*
// @include      https://*twibooru.org/*
// @include      https://*ponybooru.org/*
// @version      6.0
// @require      https://raw.githubusercontent.com/KATC14/useful/master/useful_things.js
// @require      https://raw.githubusercontent.com/soufianesakhi/node-creation-observer-js/master/release/node-creation-observer-latest.js
// ==/UserScript==

// http://orig13.deviantart.net/d1b5/f/2017/079/6/7/derpy_by_theshadowartist100_by_vcsajen-db2xkv3.png

(function() {
  //--------------------------------------------Settings--------------------------------------------
  //----------------------------------------------vvvv----------------------------------------------

  //if dot AND FNC is false colored will be false
  const Colored = true; //change this to false if you don't like colors
  const FNC = false; //true  - full name will be coloured
  //                   false - only marker will be coloured
  const ABP = true; //change this to false if you don't wish add "(Background Pony)" to the end of anon's "names"
  const Style = true //adds "title" like background pony label
  //------------------------------------------------------------------------------------------------
  //       Do not change this  (if your a user. Programmers and/or scripters can change this)
  //----------------------------------------------vvvv----------------------------------------------
  const names1 = ["", "8-bit", "A Fucking", "Aero", "Air", "Almond", "Alpha", "Amaranthine", "Amber", "American", "Annoying", "Apple", "Apricot", "Aqua", "Asian", "Astral", "Awesome", "Bad", "Based", "Beauty", "Beige", "Bell",
    "Belle", "Berry", "Beta", "Big", "Bitter", "Black", "Blaze", "Blazing", "Blue", "Bold", "Bon", "Boop the", "Bright", "Brisk", "Broken", "Bronze", "Brown", "Candy", "Caramel", "Careless", "Carrot", "Charming",
    "Cherry", "Chilly", "Chimmy", "Choco", "Chocolate", "Chromatic", "Chubby", "Citric", "Classic", "Clean", "Clear", "Clever", "Cloudy", "Cocky", "Coco", "Cold", "Cool", "Copper", "Corky", "Correct", "Cosmic", "Cranky",
    "Crazy", "Cringe", "Curly", "Cute", "Cutie", "DJ", "Daring", "Dark", "Da’", "Deadly", "Delta", "Derpy", "Desert", "Desired", "Diamond", "Dim", "Dirty", "Ditzy", "Dizzy", "Doctor", "Double", "Drama", "Drunk", "Dusk",
    "Eastern", "Easy", "Emerald", "Empress", "Epic", "European", "Fancy", "Fantastic", "Fast", "Fat", "Fifth", "Filthy", "First", "Flash", "Flirtatious", "Fluffy", "Flutter", "Foggy", "Fourth", "Full", "Funny", "Fuzzy",
    "Gamma", "Gandalf", "General", "Gentle", "Ginger", "Glass", "Glitter", "Golden", "Good", "Gotta", "Granny", "Gray", "Green", "Half", "Half Baked", "Half of a", "Handsome", "Happy", "Hard", "Hasty", "Heavy",
    "Hematite", "High", "Hitch", "Holly", "Honey", "Horny", "Hot", "Hyper", "Ice", "Igneous", "Innocent", "Iron", "Ivory", "Izzy", "Jasper", "Large", "Last", "Lauren", "Lavender", "Legendary", "Lemon", "Lemony",
    "Liberty", "Light", "Lightning", "Lil'", "Lilac", "Literally", "Little", "Lone", "Long", "Long John", "Lovely", "Low", "Lucky", "Main", "Malachite", "Melo", "Metal", "Meteor", "Mini", "Misty", "Mixed", "Moon",
    "Mr.", "Mrs.", "Ms.", "Mud", "Multicolored", "My Little", "Mysterious", "Mythical", "Navy", "Neat", "Neck", "Neon", "Night", "Nightmare", "Noisy", "Northern", "Nurse", "Nyan", "Old", "Olive", "Omega", "Onyx",
    "Orange", "Over", "Paper", "Party", "Peachy", "Pear", "Pearl", "Perfect", "Pink", "Pinkie", "Pipp", "Platinum", "Plumy", "Praise the", "Princess", "Professor", "Proud", "Pure", "Purple", "Quartz", "Queen", "Quick",
    "Rainbow", "Rainy", "Really Really Really Really Really Really Really Really Really Really Really Long", "Red", "Rosy", "Rrrrrrrrrreeeeeeeeeaaaaaaaaalllllllllyyyyyyyyy Ssssssssslllllllllooooooooowwwwwwwww", "Ruby",
    "Ruff", "Sad", "Sapphire", "Saucy", "Sea", "Second", "Shadow", "Sharp", "Sheriff", "Shining", "Short", "Shy", "Silken", "Silver", "Simply", "Slow", "Smart", "Smooth", "Snappy", "Sneaky", "Soft", "Sonic", "Sonic the",
    "Southern", "Speedy", "Spicy", "Starry", "Stella", "Stellar", "Stellate", "Stinkin'", "Stolid", "Strict", "Strong", "Sugar", "Sunny", "Super", "Supercharged", "Sus", "Sweet", "Tasty", "The Great and Powerful",
    "The Headless", "The Real", "Third", "Thunder", "Timid", "True", "True True", "Turquoise", "Twilight", "Under", "Vanilla", "Violet", "Warning", "Western", "Whinny", "White", "Windy", "Winy", "Yellow", "Zipp"
  ];

  const names2 = ["Angel", "Apple", "Apples", "Armor", "Armour", "Assassin", "Autumn", "Barry", "Bearded", "Beauty", "Bee", "Beetle", "Bell", "Belle", "Berries", "Blade", "Blink", "Bloom", "Blossom", "Bomb", "Bon", "Bone", "Bones",
    "Book", "Boom", "Boomer", "Bread", "Bridle", "Brooch", "Brook", "Bubble", "Bubbles", "Bug", "Bun", "Bunny", "Butterfly", "Button", "Cadance", "Cake", "Candle", "Candy", "Cargo", "Cat", "Celestia", "Chad", "Changa",
    "Charge", "Cherry", "Chungus", "Cider", "Class", "Clearing", "Cloud", "Cola", "Comet", "Computer", "Cook", "Coomer", "Crasher", "Crate", "Cream", "Creeper", "Crown", "Crush", "Crusher", "Cupcake", "Cupcakes",
    "Curse", "Daiquiri", "Dance", "Dancer", "Dash", "Dasher", "Dashie", "Dashy", "Day", "Days", "Deal", "Derp", "Dessert", "Devil", "Dew", "Diamond", "Do", "Dog", "Dovahkiin", "Dream", "Dress", "Drop", "Dubstep", "Dust",
    "Dusty", "Earring", "Eclair", "Egg", "Emerald", "Envy", "Eye", "Eyes", "Factory", "Faith", "Fall", "Faust", "Fear", "Feather", "Feathers", "Fire", "Flag", "Flame", "Flames", "Flare", "Floor", "Flower", "Flowers",
    "Flyer", "Folder", "Forest", "Fork", "Friend", "Frost", "Glass", "Ground", "Halo", "Harvest", "Hawk", "Hay", "Hayseed", "Haze", "Head", "Heart", "Hills", "Hoof", "Hooves", "Hope", "Horn", "Horns", "Horseman",
    "Horseshoe", "Horseshoes", "Hunt", "Hunter", "Image", "In Socks", "Is Kill", "Jack", "Jam", "Jazz", "Journal", "Kettle", "Key", "Kill", "Kills", "Knife", "Knight", "Ladle", "Lady", "Lake", "Lamp", "Leaf", "Lemon",
    "Lemonade", "Light", "List", "Loaf", "Love", "Luna", "Macintosh", "Mane", "Mess", "Mi Amore Cadenza", "Miner", "Mint", "Mints", "Mist", "Moon", "Moonbow", "Mouse", "Muffin", "Music", "Necklace", "Needle", "News",
    "Night", "Nights", "Noon", "Note", "Notes", "Nova", "Of Harmony", "Patty", "Pepper", "Petals", "Picnic", "Picture", "Pie", "Pirate", "Pixel", "Poke", "Pon3", "Pony", "Pop", "Popper", "Pride", "Prism", "Prod", "Punk",
    "Rainbow", "Rat", "Reaper", "Rice", "Ring", "Rock", "Roll", "Romance", "Rosette", "Ruby", "Runner", "Saddle", "Sapphire", "Scapula", "Sebastian", "Shield", "Shimmer", "Shine", "Shovel", "Shower", "Shy", "Signal",
    "Skies", "Sky", "Slapjack", "Slim Shady", "Snap", "Snow", "Song", "Soul", "Sparkle", "Sparky", "Spawn", "Sphere", "Spider", "Spin", "Spirit", "Spoon", "Spring", "Stairs", "Star", "Stars", "Starscout", "Stool",
    "Storm", "Strike", "String", "Strings", "Stripe", "Stripes", "Stuff", "Summer", "Sun", "Swirl", "Sword", "Swords", "Table", "Tart", "The Bard", "The Changeling", "The Damned", "The Diamond Dog", "The Eternal",
    "The Grey", "The Horse", "The White", "Tiara", "Time", "Times", "Top", "Trailblazer", "Tree", "Trees", "Trixie", "Tron", "Twilight", "Twist", "Virgin", "Vise", "Was Not The Imposter", "Water", "Waterfall", "Wheat",
    "Wind", "Window", "Wing", "Wings", "Winter", "Wolf", "Zoomer"
  ];

  const names3 = ['5000 Candles On The Wind', 'An Actual Horse', 'Angel', 'Apple', 'Applejack', 'Anonymous', 'Anonfilly', 'Autumn', /*'Background Pony', */ 'Beardy', 'Beast', 'Bee', 'Beetlejuice', 'Berry', 'Black Knight', 'Blade',
    'Blink', 'Blossom', 'Bomberman', 'Bon Bon', 'Bond. James Bond.', 'Bone Daddy', 'Book', 'Boomer', 'Boop', 'Bread', 'Brooch', 'Brook', 'Bubble', 'Bubbles', 'Bug', 'Bunny', 'Buttercup', 'Button', 'Cake', 'Candleja-',
    'Cadance', 'Cat', 'Celestia', 'Chad Spike', 'Charge', 'Cherry', 'Chungus', 'Cider', 'Clearing', 'Cloud', 'Comet', 'Computer', 'Cook', 'Coomer', 'Crasher', 'Crate', 'Cream', 'Creeper', 'Crown', 'Crush', 'Crusher',
    'Cupcake', 'Curse', 'Daiquiri', 'Dancer', 'Dash', 'Dashie', 'Deal Or No Deal', 'Derpy', 'Dessert', 'Deviled Eggs', 'Diamond', 'Diabeetus', 'Dovahkiin', 'Dress', 'Drop', 'Dubstep', 'Dusty', 'Earring', 'Eclair',
    'Elmo', 'Egg', 'Eragon', 'Emerald', 'Envy', 'Eye', 'Exodia The Forbidden One', 'Factory', 'Faith', 'Fall', 'Fear', 'Feathers', 'Fire', 'Flame', 'Flare', 'Floor Bored', 'Flowers', 'Flutterguy', 'Flyer',
    'Fool of a Took!', 'Forest Gump', 'Fork', 'Frost', 'Glass', 'Got Milk?', 'Ground', 'Halo', 'Harvest', 'Hawk', 'Hay Guys', 'Haze', 'Head', 'Heart', 'Help I\'m Trapped In A Username Making Factory', 'Hills',
    'Hoof', 'Hooves Hooves', 'Hope', 'Horny Jail', 'Horseshoe', 'hunter2', 'iMacintosh', 'Imaginary Friend', 'IWTCIRD', 'Incognito', 'Jake From State Farm', 'Jazz', 'Joy', 'Kettle', 'Kimba the White Lion', 'Killer',
    'Knoife', 'Ladle', 'Lady', 'Lake', 'Lamp', 'Leaf', 'Left Shark', 'Lemony Snicket', 'Lemonade', 'Lighthoof', 'Listen!', 'Loaf', 'Look At This Photograph', 'Love', 'Mane 6', 'Messiah', 'Mike Hunt', 'Minor', 'Minty',
    'Misty', 'Moon', 'Moonpie', 'Mouse', 'Mtn Dew', 'Muffin', 'Neckbeard', 'Needledick', 'Newsflash', 'Night', 'Note:', 'Nova Prospekt', 'NukaCola', 'Numa Numa', 'Omellette Du Fromage', 'One Ring To Rule Them All',
    'Pattycake', 'Peanut Butter Jelly Time', 'Petals', 'Pepper', 'Picnic', 'Pikachu', 'Pie', 'Pirate', 'Pixel', 'Pon3', 'Pony', 'Pride Rock', 'Prism', 'Punk', 'Rainbow', 'Rat', 'Rawr', 'Reaper', 'Rice', 'Rock', 'Roll',
    'Romance', 'Rosetta Stoned', 'Ruby', 'Runner', 'Saddle', 'Saphira', 'Scruffy', 'Shielded', 'Shut', 'Shine', 'Shovel', 'Shower', 'Signal', 'Clear Skies a Cute', 'Slim Shady', 'Snapped', 'Snow', 'Soul', 'Sparkler',
    'Spawnling', 'Spider-Man', 'Spin to Win', 'Spirit: Stallion of the Cimarron', 'Spoonman', 'Sproing', 'Stairs', 'Starkiller', 'Stool', 'Stormbreaker', 'Striker', 'Stringcheese', 'Stripes', 'Stuff', 'Summer', 'Sun',
    'Sweep Sweep Sweep Sweep', 'Swirl', 'Sword', 'Table', 'Tard', 'The Cutie Mark Crusaders', 'The Fun Has Been Doubled!', 'The Imposter', 'The Sun Is A Deadly Lazer', 'The Old One', 'This is a sign.', 'Time',
    'Todd Howard', 'Trailblazer', 'Treebeard', 'Trixie', 'Tron Legacy', 'Twiggie', 'Twist', 'Virginia', 'Vice City', 'Wake up Pickle', 'Waterga', 'Waterfall', 'Wheat', 'White Knight', 'Who Is This Four Chan', 'Whorse',
    'Wind Waker', 'Windows 98', 'Winter', 'what the hay', 'Wolf In Sheep\'s Clothing', 'Wojak', 'You Are Now Breathing Manually', 'Zoidberg', 'Zoinks'
  ];

  const searchRER = new RegExp('(Background (?:Pony|Bat)|Anonymous) #([0-9A-F])([0-9A-F])([0-9A-F])([0-9A-F])');
  //var searchRER = new RegExp('Background Pony #([0-9A-F]{2})([0-9A-F]{2})', '');

  NodeCreationObserver.onCreation(`.small-text > strong, .communication__body__text > blockquote > a, .communication__body__sender-name, .communication__body__text > a, .table > tbody > tr > td > strong,
.image_uploader > strong, .block__header__item > strong, .comment_backlinks > a, .paragraph > a, .profile-top__name-header, .label--primary, .markdown-container > p > a`, start, false); //,.communication__body__text
  if (window.location.href.includes('twibooru.org')) {
    addGlobalStyle(`body{line-height: 1.15em;}`)
  }

  function start(Node) {
    if (Node.innerHTML.includes("#") && Style && Colored && Node.className.includes("label--primary")) {
      var BPtag = Node.innerHTML.split("#")[1]
      if (!BPtag.includes(" ")) {
        console.log('"title"', BPtag)
        Node.className += `background-pony Background-Pony-${BPtag}`
        var SpanRgb = `#${getRGBstr(BPtag)}`;
        Node.style.color = TCC(hexToRgb(SpanRgb))
        addGlobalStyle(`.Background-Pony-${BPtag}{background:${SpanRgb} !important}`)
      }
    }
    var match = Node.innerHTML.match(searchRER);
    if (match && Node.innerHTML.includes("#")) {
      if (Node.tagName == 'A' || Node.tagName == 'H1') {
        try {var BPtag = Node.innerHTML.split("#")[1].split("'")[0]}
        catch (error) {
          var BPtag = Node.innerHTML.split("#")[1]
          console.error('error', error)
        }
      }
      else {var BPtag = Node.innerHTML.split("#")[1];}
      try {BPtag = BPtag.split("<")[0]} catch (error) {console.error('error', error)}
      var SpanRgb = `#${getRGBstr(BPtag)}`;
      BPNameCreation(Node, match, BPtag, SpanRgb)
      if (Node.childNodes[0].tagName == 'A') {
        var Nodehref = Node.childNodes[0].href
        var element = document.createElement("A");
        element.href = Nodehref
        Node.parentNode.insertBefore(element, Node.parentNode.childNodes[0])
        Node.style.display = 'none'
        Node = element
        if (Node.tagName == 'H1') {
          document.getElementsByTagName('title')[0].innerHTML = `${Node.innerHTML}`
        }
      }
      if (Style) {
        if (Node.className == "communication__body__sender-name" && Node.className != 'communication__body__text') {
          var div = document.createElement("div");
          div.className = `label label--block label--small label--primary background-pony Background-Pony-${BPtag}`
          div.innerHTML = "Background Pony"
          Node.parentNode.insertBefore(div, Node.parentNode.childNodes[2])
          if (window.location.href.includes('twibooru.org')) {
            Node.parentNode.insertBefore(document.createElement("br"), Node.parentNode.childNodes[2])
          }
        }
      }
    }
  }

  function BPNameCreation(Node, match, BPtag, SpanRgb) {
    const index1 = parseInt(match[2] + match[3], 16);
    const index2 = parseInt(match[4] + match[5], 16);
    const index3 = parseInt(match[2] + match[4], 16);
    if (!match.isnull) {
      if (index3 % 8 == 0) {var name = names3[index1]
      } else {var name = `${names1[index1]} ${names2[index2]}`}
      console.log(`names ${(index3 % 8 == 0) ? 'rare!' :'normal'} "${BPtag}" ${name}`)
      if (Colored) {
        addGlobalStyle(`.Background-Pony-Dot-${BPtag}{color:${SpanRgb}}`)
        addGlobalStyle(`.Background-Pony-${BPtag}{background:${SpanRgb} !important; color:${TCC(hexToRgb(SpanRgb))}}`)
      }
      const className = (Colored) ? `Background-Pony-Dot-${BPtag}` : '';
      const spanBefore = (FNC) ? '' : `${name} `; /*full Name Color*/
      //var spanInner =    (FNC) ? (ABP && FNC) ? `${name}  (Background Pony)` : name : '•';                /*full Name Color*/
      if (FNC) {
        if (ABP && FNC) {var spanInner = `${name}  (Background Pony)`}
        else {           var spanInner = name}
      }
      else {             var spanInner = '•'}
      var spanAfter = (ABP && !FNC) ? '  (Background Pony)' : ''; /*add Background Pony*/

      Node.innerHTML = Node.innerHTML.replace(searchRER, `${spanBefore}<span title="${BPtag}" class="${className}">${spanInner}</span>${spanAfter}`)
    } else {return null}
  }

  function getRGBstr(color16bit) {
    var pixel = parseInt(color16bit, 16);

    // Expand to 8-bit values.
    var red = (pixel & 0xF800) >> 11 << 3;
    var green = (pixel & 0x7E0) >> 5 << 2;
    var blue = (pixel & 0x1F) << 3;
    return ((1 << 24) + (red << 16) + (green << 8) + blue).toString(16).slice(1);
  }
})();
