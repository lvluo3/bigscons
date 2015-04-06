src_file1 = Glob('./*.cc')
src_file2 = Glob('../err_handle/*.c')
src_file3 = Glob('../udpserver/*.c')
src_file4 = Glob('../wrap_base/*.c')
src_file5 = Glob('../data_structure/hash_al/*.c')

src_file = src_file1 + src_file2 + src_file3 + src_file4 +src_file5

inc = ['.' , '../common' , '../../lib/x264/libx264_124/include' , '../../lib/baseLib/include' , '../../lib/avs/lencod' , '../../lib/x264/libx264_124/lib','../../lib/audio/mp2',
		'../../lib/avs/AdaptLayer' ,]

libs = ['mysqlclient' ,'pthread','dl','m','samplerate','faac','faad','dec_hwaacld','g729a','avcodec','avutil','mysqlclient' , 'pubd' , 'avsen' , 'mp2' , 'video' , 'avs']

env = Environment()

hello=env.StaticLibrary('libpubd.a' , src_file1 , CPPPATH = inc , CC = ['g++'] , LIBS = libs , 
LIBPATH = ['/usr/lib64/mysql' , '../../lib/avs/lencod','../../lib/baseLib/lib/','../../lib/audio/lib/' ,'../../lib/x264/libx264_124/lib/','../../lib/avs/AdaptLayer/'],
CCFLAGS = ['-std=gnu++0x','-g'] 
#['-g' , '-ggdb','-Wall','-DHAVE_CONFIG_H','-Wl,--hash-style=sysv','-std=c++0x'] ,
#LINKFLAGS = ['-g' , '-rdynamic' ,'-ggdb','-Wall','-DHAVE_CONFIG_H','-Wl,--hash-style=sysv','-std=c++0x'],
#LDFLAG = ['-ggdb','-Wall','-DHAVE_CONFIG_H','-Wl,--hash-style=sysv','-std=c++0x','-g']
#LIBS = ['g729a'] , LIBPATH = ['.']
# LDFLAG = ['-g']
)


#SharedLibrary('so' , 'so1.c')
#StaticLibrary('so','so1.c')

#run shell
#cp = env.Command('xxx' ,[] ,'cp *.so ../../../debug/test/ -rf')


#scons install
xxx = Glob('./*.so')
#env.Install(dir = "../../../debug/test/", source =xxx)
env.Install(dir = "/root/WSISGW/balm/lib/baseLib/lib", source = hello)
env.Alias('install', ['/root/WSISGW/balm/lib/baseLib/lib'])


