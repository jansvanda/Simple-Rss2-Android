Simple-Rss2-Android
===================

A really simple RSS 2.0 Parser Library for Android. For easier use it also includes an asynchronous call to get feeds in the background and nofies the UI thread using a callback object.

Example:
`````java
SimpleRss2Parser parser = new SimpleRss2Parser("http://pingeb.org/feed", 
	new SimpleRss2ParserCallback() {
		@Override
		public void onFeedParsed(List<RSSItem> items) {
			for(int i = 0; i < items.size(); i++){
				Log.d("SimpleRss2ParserDemo",items.get(i).getTitle());
			}
		}
		@Override
		public void onError(Exception ex) {
			Toast.makeText(mContext, ex.getMessage(), Toast.LENGTH_SHORT).show();
		}
	};
);
parser.parseAsync();
`````
