# hideClassLoder
> hide loaders

## implement

``` java
public static Object getDexClassLoader(Context context, String path) {
    try {
        String dc = "dalvik.system.DexClassLoader";
        Class c = getClass("java.lang.ClassLoader");
        if (c != null) {
            Class[] types = new Class[]{String.class, String.class, String.class, c};
            Object[] values = new Object[]{path, context.getCacheDir().getAbsolutePath(), null, invokeObjectMethod(context, "getClassLoader")};
            return newInstance(dc, types, values);
        }
    } catch (Throwable igone) {
    }
    return null;
}

```

* `反射可用工具库`: [ReflectFun](https://github.com/hhhaiai/ReflectFun)

