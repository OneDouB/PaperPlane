创建新项目替换src
通过ShootGame运行

点击鼠标开始游戏

ShootGame类
    主程序类，包含运行方法main
    设定窗口，导入静态资源，初始化变量，声明常量

    包含方法
        paint():绘制图像界面
        paintHero():绘制英雄机
        paintBullets():绘制子弹
        paintFlyingObjects():绘制飞行物
        paintScore():绘制分数与命数
        paintState():绘制程序状态
        main():创建程序窗口，启动执行
        action():程序运行时代码，监听鼠标操作
            子方法
            mouseMoved():鼠标移动，将鼠标位置赋值给英雄机
            mouseEntered():鼠标进入窗口，如果在暂停状态解除暂停
            mouseExited():鼠标退出窗口，如果处于运行状态进行暂停
            mouseClicked():鼠标点击，如果处于启动状态进入运行状态，如果处于结束状态清空进程返回启动状态
            run():进行进程状态更新，判定检测，刷新图像界面
        enterAction():生成一个飞行物
        stepAction():更新实体状态，调用各实体step方法
        flyingStepAction():非子弹与英雄机的实体更新
        shootAction():英雄机的射击行为，创建新子弹实体
        bangAction():子弹命中碰撞检测，碰撞则删除子弹和飞行物
        putOfBoundsAction():子弹和飞行物的越界处理
        checkGameOverAction:游戏结束检测
        isGameOver():游戏结束判定
        bang():飞行物与子弹的碰撞判定
        nextOne():随机生成飞行物
FlyingObject类
    飞行物类，抽象类
    包含飞行物的基本信息声明，基本方法声明定义，抽象方法声明
    参数：x\X坐标;y\Y坐标;width\碰撞盒宽,height\碰撞盒高,image\图像;
    子方法
        getX():
        setX():
        getY():
        setY():
        getWidth():
        setWidth():
        getHeight():
        setHeight():
        getImage():
        setImage():
        shootBy():
    抽象方法
        outOfBounds():
        step():
Enemy接口
    敌人应实现的接口，包含敌人应实现的抽象方法
    抽象方法
        getScore():
Award接口
    奖励应实现的接口；包含奖励应有的参数和应实现的抽象方法
    常量：DOUBLE_FIRE = 0; LIFE = 1;\奖励类型绑定数值
    抽象方法
        getType():
Hero类
    英雄机类
    继承FlyingObject类，英雄机特化参数声明，特化方法声明定义，父类抽象方法实现
    参数：images[]\英雄机图片组;index\英雄机图片索引;doubleFire\双倍火力弹药数;life\命数;
    子方法
        Hero():初始化英雄机
        isDoubleFire():双倍火力判定
        setDoubleFire():设置双倍火力
        addDoubleFire():增加双倍火力
        addLife():
        subtractLife():
        getLife():
        moveTo():将英雄机移至鼠标位置
        shoot():发射子弹
        hit():碰撞判定
    实现方法
        outOfBounds():
        step():
Airplane类
    敌飞机类
    继承FlyingObject类，实现Enemy接口，声明特化参数，声明定义特化方法，实现抽象方法
    参数：speed = 3;\敌飞机移动速度
    子方法
        Airplane():初始化敌飞机
    实现方法
        getScore():击毁分数
        outOfBounds():
        step():移动
Bee类
    蜜蜂类
    继承FlyingObject类,实现Award接口，声明特化参数，声明定义特化方法，实现抽象方法
    参数：xSpeed = 1\X轴移动速度;ySpeed = 2\Y轴移动速度;awardType\奖励类型;
    子方法
        Bee():初始化蜜蜂
        getType():
    实现方法
        outOfBounds():
        step():
Bullet类
    子弹类
    继承FlyingObject类,声明特化参数，声明定义特化方法，实现抽象方法
    参数：Speed = 3；\移动速度
    子方法
        bullet():初始化子弹
    实现方法
        step():
        outOfBounds():





