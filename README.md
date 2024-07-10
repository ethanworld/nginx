```
./auto/configure --prefix=/home/learning/nginx
make
```

# 关于定时器
nginx中的定时器是放在一个全局的叫做ngx_event_timer_rbtree的红黑树中的，通过ngx_add_timer来添加定时器，等超时定时事件执行完后就从红黑树中移除该定时器，所以想要达到循环定时的目的，那就需要每次在执行定时操作后再次通过ngx_add_timer添加到定时列表中。
