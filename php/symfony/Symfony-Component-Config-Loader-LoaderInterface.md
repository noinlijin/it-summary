type loaderInterface interface{
   //用某个资源加载xx东西,加载的类型是xx 返回一个加载后的配置对象
   load(resource interface{},type string)interface{}
   supports(resource interface{},type string) bool
   getResolver() LoaderResolverInterface
   setResolver(resolver LoaderResolverInterface)
}
type LoaderResolverInterface interface{
  resolve(resource interface{},type string)(LoaderInterface)
}

resource -> 从某个资源上加载东西,
type -> 类型如 annotation

Resolver 是在一些加载器里面找到一个可以加载这个东西的加载器

1.配置->分析由哪个加载器加载->加载配置->返回配置对象