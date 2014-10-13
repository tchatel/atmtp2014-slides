!SLIDE subsection ================

# Plan

!NOTES ---------------------------
- au sens littéraire : structure d'un texte, schéma


!SLIDE ===========================

# objectif :
## rendre le plan évident


!SLIDE ===========================

## mettre en avant la structure


!SLIDE smallcode ===========================

# if / ? :
### structure / expression

    parts.push(isNegative ? pattern.negPrefix
                        : pattern.posPrefix);
    parts.push(formatedNumber);
    parts.push(isNegative ? pattern.negSuffix
                        : pattern.posSuffix);
    return parts.join('');


!SLIDE smallcode ===========================

### JavaScript

    xhr.send(post || '');

### Groovy

    def streetName = user?.address?.street


!SLIDE ===========================

TODO
* limiter les imbrications au maximum
* cacher les détails
* niveau d'abstraction cohérent


!SLIDE smallestcode ===========================

    public T newInstance()
            throws InstantiationException, IllegalAccessException {
        if (System.getSecurityManager() != null) {
            checkMemberAccess(Member.PUBLIC, ClassLoader.getCallerClassLoader());
        }
        return newInstance0();
    }

    private T newInstance0()
            throws InstantiationException, IllegalAccessException {
        // NOTE: the following code may not be strictly correct under
        // the current Java memory model.

        // Constructor lookup
        if (cachedConstructor == null) {
            if (this == Class.class) {
                throw new IllegalAccessException(
                    "Can not call newInstance() on the Class for java.lang.Class"
                );
            }
            try {
                Class[] empty = {};
                final Constructor<T> c = getConstructor0(empty, Member.DECLARED);
                // Disable accessibility checks on the constructor
                // since we have to do the security check here anyway
                // (the stack depth is wrong for the Constructor's
                // security check to work)
                java.security.AccessController.doPrivileged
                    (new java.security.PrivilegedAction() {
                            public Object run() {
                                c.setAccessible(true);
                                return null;
                            }
                        });
                cachedConstructor = c;
            } catch (NoSuchMethodException e) {
                throw new InstantiationException(getName());
            }
        }
        Constructor<T> tmpConstructor = cachedConstructor;
        // Security check (same as in java.lang.reflect.Constructor)
        int modifiers = tmpConstructor.getModifiers();
        if (!Reflection.quickCheckMemberAccess(this, modifiers)) {
            Class caller = Reflection.getCallerClass(3);
            if (newInstanceCallerCache != caller) {
                Reflection.ensureMemberAccess(caller, this, null, modifiers);
                newInstanceCallerCache = caller;
            }
        }
        // Run constructor
        try {
            return tmpConstructor.newInstance((Object[])null);
        } catch (InvocationTargetException e) {
            Unsafe.getUnsafe().throwException(e.getTargetException());
            // Not reached
            return null;
        }
    }
    private volatile transient Constructor<T> cachedConstructor;
    private volatile transient Class       newInstanceCallerCache;

TODO enlever fond noir !


!SLIDE smallestcode ===========================

    public T newInstance()
            throws InstantiationException, IllegalAccessException {

        if (System.getSecurityManager() != null) {
            checkMemberAccess(Member.PUBLIC, ClassLoader.getCallerClassLoader());
        }
        Constructor<T> tmpConstructor = getConstructor();
        checkConstructorAccess(tmpConstructor);
        return runConstructor(tmpConstructor);
    }

    private Constructor<T> getConstructor()
            throws InstantiationException, IllegalAccessException {
        if (cachedConstructor == null) {
            // Constructor lookup
            if (this == Class.class) {
                throw new IllegalAccessException(
                    "Can not call newInstance() on the Class for java.lang.Class"
                );
            }
            try {
                Class[] empty = {};
                final Constructor<T> c = getConstructor0(empty, Member.DECLARED);
                // Disable accessibility checks on the constructor
                // since we have to do the security check here anyway
                // (the stack depth is wrong for the Constructor's
                // security check to work)
                java.security.AccessController.doPrivileged
                    (new java.security.PrivilegedAction() {
                            public Object run() {
                                c.setAccessible(true);
                                return null;
                            }
                        });
                cachedConstructor = c;
            } catch (NoSuchMethodException e) {
                throw new InstantiationException(getName());
            }
        }
        return cachedConstructor;
    }

    private void checkConstructorAccess(Constructor<T> constructor)
            throws InstantiationException, IllegalAccessException {
        // Security check (same as in java.lang.reflect.Constructor)
        int modifiers = constructor.getModifiers();
        if (!Reflection.quickCheckMemberAccess(this, modifiers)) {
            Class caller = Reflection.getCallerClass(3);
            if (newInstanceCallerCache != caller) {
                Reflection.ensureMemberAccess(caller, this, null, modifiers);
                newInstanceCallerCache = caller;
            }
        }
    }

    private T runConstructor(Constructor<T> constructor)
            throws InstantiationException, IllegalAccessException {
        try {
            return constructor.newInstance((Object[])null);
        } catch (InvocationTargetException e) {
            Unsafe.getUnsafe().throwException(e.getTargetException());
            // Not reached
            return null;
        }
    }

    private volatile transient Constructor<T> cachedConstructor;
    private volatile transient Class       newInstanceCallerCache;

TODO enlever fond noir !


