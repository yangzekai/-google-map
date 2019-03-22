# -google-map
利用高德地图显示google map
https://www.jianshu.com/p/df3865ac9af7
&FY3oBoj6NOXyQJ9Kr9CqY+77foUP0JuVzSJeBTU9QJs=&
public class GoogleMapUtil {          
final static String url = "http://mt2.google.cn/vt/lyrs=y@167000000&hl=zh-CN&gl=cn&x=%d&y=%d&z=%d&s=Galil";
public static TileOverlayOptions getGooleMapTileOverlayOptions() {
        TileProvider tileProvider = new UrlTileProvider(256, 256) {
            public URL getTileUrl(int x, int y, int zoom) {
                try {
                    return new URL(String.format(url, x, y, zoom));
                } catch (MalformedURLException e) {
                    e.printStackTrace();
                }
                return null;
            }
        };
&FY3oBoj6NOXyQJ9Kr9CqY+77foUP0JuVzSJeBTU9QJs=&
        return new TileOverlayOptions()
                .tileProvider(tileProvider)
                .diskCacheEnabled(true)
                .diskCacheSize(100000)
                .diskCacheDir(Configuration.getAppContext().getExternalCacheDir().getAbsolutePath())
                .memoryCacheEnabled(false)
                .zIndex(-9999);
    }
    &FY3oBoj6NOXyQJ9Kr9CqY+77foUP0JuVzSJeBTU9QJs=&
}
&FY3oBoj6NOXyQJ9Kr9CqY+77foUP0JuVzSJeBTU9QJs=&
aMap.addTileOverlay(GoogleMapUtil.getGooleMapTileOverlayOptions());
&FY3oBoj6NOXyQJ9Kr9CqY+77foUP0JuVzSJeBTU9QJs=&
