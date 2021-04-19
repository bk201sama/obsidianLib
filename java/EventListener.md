# 简介
所有事件侦听器接口必须扩展的标记接口 [[marker annotation]]
比如定义事件（事件基类[[EventObject]]）
``
public interface DoorListener extends EventListener { 
public void doorEvent(DoorEvent event);
}
``
然后实现接口;也可以不实现，使用匿名函数
``
public class DoorListener1 implements DoorListener {
    @Override public void doorEvent(DoorEvent event) {
        if (event.getDoorState() != null && event.getDoorState().equals("open")) {
            System.out.println("门1打开");
        } else {
            System.out.println("门1关闭");
        }
    }
}
``
搞个事件管理器，其中有事件注册功能和事件通知功能
``
public class DoorManager {
    private Collection listeners;

    /**
     * 添加事件
     * 
     * @param listener
     *            DoorListener
     */
    public void addDoorListener(DoorListener listener) {
        if (listeners == null) {
            listeners = new HashSet();
        }
        listeners.add(listener);
    }

    /**
     * 移除事件
     * 
     * @param listener
     *            DoorListener
     */
    public void removeDoorListener(DoorListener listener) {
        if (listeners == null)
            return;
        listeners.remove(listener);
    }

    /**
     * 触发开门事件
     */
    protected void fireWorkspaceOpened() {
        if (listeners == null)
            return;
        DoorEvent event = new DoorEvent(this, "open");
        notifyListeners(event);
    }

    /**
     * 触发关门事件
     */
    protected void fireWorkspaceClosed() {
        if (listeners == null)
            return;
        DoorEvent event = new DoorEvent(this, "close");
        notifyListeners(event);
    }

    /**
     * 通知所有的DoorListener
     */
    private void notifyListeners(DoorEvent event) {
        Iterator iter = listeners.iterator();
        while (iter.hasNext()) {
            DoorListener listener = (DoorListener) iter.next();
            listener.doorEvent(event);
        }
    }
}
``
最后主线程直接调用注册后执行通知