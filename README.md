import { Button } from "@/components/ui/button";
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import { Calendar, Mountain, Users, Compass, Star, Quote, Zap, MapPin } from "lucide-react";
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";

// ⚠️ Asegúrate de que estas rutas de imágenes sean correctas en tu proyecto.
import heroImage from "@/assets/hero-cistierna.jpg"; 
import activity1 from "@/assets/activity-trekking.jpg";
import activity2 from "@/assets/activity-climbing.jpg";
import logoSocio from "@/assets/logo-socio.png"; // Asumiendo que tienes un logo de socio

// --- 1. Datos del Club ---
const clubData = {
  city: "Cistierna",
  established: 1995,
  membersCount: "200+",
};

// --- 2. Datos de Actividades (más descriptivos) ---
const upcomingActivities = [
  {
    date: "01/02/2026",
    title: "Ruta Raquetas: Pico Cueto",
    level: "Media-Alta",
    duration: "1 día",
    description: "Travesía invernal técnica por las cumbres de la Montaña Palentina. Se requiere experiencia y equipo de seguridad.",
    image: activity1,
  },
  {
    date: "15/02/2026",
    title: "Curso Básico de Orientación",
    level: "Baja",
    duration: "2 días",
    description: "Taller intensivo de fin de semana para dominar mapa, brújula y navegación GPS en la Montaña Oriental.",
    image: activity2,
  },
];

// --- 3. Datos de Testimonios ---
const testimonials = [
    {
        quote: "El Club Los Rejos no solo ofrece rutas increíbles, sino una comunidad de apoyo. Me siento mucho más segura en la montaña desde que me uní.",
        author: "María G.",
        activity: "Socia desde 2022",
    },
    {
        quote: "La organización de las travesías es impecable y la formación en seguridad que ofrecen es de primer nivel. ¡Un 10!",
        author: "Javier R.",
        activity: "Curso de Invierno 2025",
    },
];

// --- Subcomponente: Card de Actividad ---
const ActivityCard = ({ activity }) => {
  const getLevelColor = (level) => {
    switch (level) {
      case "Baja": return "bg-green-600 hover:bg-green-700";
      case "Media-Alta": return "bg-yellow-600 hover:bg-yellow-700";
      case "Alta": return "bg-red-600 hover:bg-red-700";
      default: return "bg-primary";
    }
  };

  return (
    <Card className="overflow-hidden group hover:shadow-2xl transition-all duration-500 border-2 border-transparent hover:border-primary/50">
      <div className="relative h-52 overflow-hidden">
        <img
          src={activity.image}
          alt={`Imagen de la actividad: ${activity.title}`}
          className="w-full h-full object-cover transition-transform group-hover:scale-105 duration-700"
          loading="lazy"
        />
        <div className={`absolute top-4 right-4 text-primary-foreground px-3 py-1 rounded-full text-sm font-bold shadow-md ${getLevelColor(activity.level)}`}>
          {activity.level}
        </div>
      </div>
      <CardHeader className="pb-3">
        <CardTitle className="text-xl font-semibold">{activity.title}</CardTitle>
        <CardDescription className="flex items-center gap-2 text-sm text-gray-600">
          <Calendar className="h-4 w-4" />
          <time dateTime={activity.date.split('/').reverse().join('-')}>{activity.date}</time> • {activity.duration}
        </CardDescription>
      </CardHeader>
      <CardContent>
        <p className="text-sm text-gray-600 mb-4 line-clamp-3">{activity.description}</p>
        <Button className="w-full font-semibold">
          Más Info y Reserva
        </Button>
      </CardContent>
    </Card>
  );
};

// --- Componente Principal: Index ---
const Index = () => {
  return (
    <div className="min-h-screen flex flex-col">
      <title>Club de Montaña Los Rejos | {clubData.city} y Picos de Europa</title>
      <Navbar />

      {/* 🏔️ Sección 1: Hero */}
      <section className="relative h-[700px] flex items-center justify-center">
        <div
          className="absolute inset-0 bg-cover bg-center"
          style={{ backgroundImage: `url(${heroImage})` }}
        >
          <div className="absolute inset-0 bg-black/60 backdrop-blur-sm" />
        </div>
        <div className="relative z-10 text-center px-4 max-w-5xl text-white">
          <Badge variant="secondary" className="mb-4 text-base bg-primary hover:bg-primary/90">
            Desde {clubData.established} en {clubData.city}
          </Badge>
          <h1 className="text-6xl md:text-7xl font-extrabold mb-6 tracking-tight drop-shadow-lg">
            La Montaña Oriental Leonesa Te Espera
          </h1>
          <p className="text-xl md:text-2xl text-gray-200 font-medium mb-10 drop-shadow-md">
            Únete a la comunidad de escaladores, senderistas y exploradores de Los Rejos.
          </p>
          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <Button size="lg" className="text-xl font-bold py-7 px-8 transition-transform hover:scale-[1.03]">
              ¡Hazte Socio Hoy!
            </Button>
            <Button size="lg" variant="outline" className="text-xl font-bold py-7 px-8 text-white border-white bg-transparent hover:bg-white/20">
              <Zap className="mr-2 h-5 w-5" /> Ver Calendario
            </Button>
          </div>
        </div>
      </section>

      {/* 💡 Sección 2: Características y Valor */}
      <section className="py-20 px-4 bg-gray-50">
        <div className="max-w-7xl mx-auto">
          <div className="text-center max-w-3xl mx-auto mb-12">
            <h2 className="text-4xl font-extrabold mb-3 text-gray-800">
              Tu Puerta a la Aventura Segura
            </h2>
            <p className="text-lg text-gray-600">
              Te ofrecemos la experiencia, el conocimiento y el compañerismo para disfrutar de la montaña al máximo.
            </p>
          </div>

          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
            <Card className="text-center p-6 border-t-4 border-primary shadow-lg">
              <Mountain className="h-10 w-10 text-primary mb-3 mx-auto" />
              <CardTitle className="text-lg">Explora la Cordillera</CardTitle>
              <CardDescription className="text-sm">Rutas únicas y guiadas por la Montaña Oriental, Picos de Europa y más.</CardDescription>
            </Card>

            <Card className="text-center p-6 border-t-4 border-yellow-500 shadow-lg">
              <Compass className="h-10 w-10 text-yellow-600 mb-3 mx-auto" />
              <CardTitle className="text-lg">Formación de Nivel</CardTitle>
              <CardDescription className="text-sm">Cursos de GPS, seguridad invernal y escalada impartidos por expertos.</CardDescription>
            </Card>

            <Card className="text-center p-6 border-t-4 border-green-500 shadow-lg">
              <Users className="h-10 w-10 text-green-600 mb-3 mx-auto" />
              <CardTitle className="text-lg">Comunidad y Amigos</CardTitle>
              <CardDescription className="text-sm">Más de {clubData.membersCount} socios. ¡La montaña se disfruta en compañía!</CardDescription>
            </Card>
            
            <Card className="text-center p-6 border-t-4 border-blue-500 shadow-lg">
              <MapPin className="h-10 w-10 text-blue-600 mb-3 mx-auto" />
              <CardTitle className="text-lg">Base en {clubData.city}</CardTitle>
              <CardDescription className="text-sm">Tu punto de encuentro y sede social en el corazón de la Montaña Leonesa.</CardDescription>
            </Card>
          </div>
        </div>
      </section>

      {/* 🗓️ Sección 3: Actividades Destacadas */}
      <section className="py-20 px-4 bg-white">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-extrabold mb-4 text-center text-gray-800">
            Próximas Aventuras
          </h2>
          <p className="text-lg text-center text-gray-600 mb-12">
            Inscríbete antes de que se agoten las plazas. ¡La aventura empieza aquí!
          </p>

          <div className="grid grid-cols-1 lg:grid-cols-2 gap-10">
            {upcomingActivities.map((activity, index) => (
              <ActivityCard key={index} activity={activity} />
            ))}
          </div>

          <div className="text-center mt-16">
             <Button size="lg" variant="default" className="text-lg font-bold py-3 px-8 shadow-lg transition-transform hover:scale-105">
                Ver Calendario Completo de 2026
             </Button>
          </div>
        </div>
      </section>

      {/* 💬 Sección 4: Testimonios */}
      <section className="py-20 px-4 bg-accent">
          <div className="max-w-7xl mx-auto">
              <h2 className="text-4xl font-extrabold mb-12 text-center text-gray-800">
                  Nuestra Comunidad Opina
              </h2>
              <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
                  {testimonials.map((t, index) => (
                      <Card key={index} className="p-6 bg-white shadow-xl">
                          <Quote className="h-8 w-8 text-primary mb-4" />
                          <p className="italic text-lg text-gray-700 mb-4 leading-relaxed">
                              "{t.quote}"
                          </p>
                          <div className="flex items-center gap-3">
                            <Star className="h-5 w-5 text-yellow-500 fill-yellow-500" />
                            <Star className="h-5 w-5 text-yellow-500 fill-yellow-500" />
                            <Star className="h-5 w-5 text-yellow-500 fill-yellow-500" />
                            <Star className="h-5 w-5 text-yellow-500 fill-yellow-500" />
                            <Star className="h-5 w-5 text-yellow-500 fill-yellow-500" />
                          </div>
                          <p className="mt-4 font-semibold text-primary">{t.author}</p>
                          <p className="text-sm text-muted-foreground">{t.activity}</p>
                      </Card>
                  ))}
              </div>
          </div>
      </section>

      {/* 🤝 Sección 5: CTA Final */}
      <section className="bg-primary py-24 px-4">
          <div className="max-w-5xl mx-auto text-center">
              <h2 className="text-4xl md:text-5xl font-extrabold text-primary-foreground mb-4">
                  ¿Listo para tu próxima cumbre en León?
              </h2>
              <p className="text-xl text-primary-foreground/90 mb-10">
                  Únete al club de montaña más antiguo de la comarca de {clubData.city} y empieza tu aventura hoy.
              </p>
              <Button size="lg" variant="outline" className="text-xl font-bold py-7 px-8 text-primary border-white bg-white hover:bg-gray-100 shadow-xl transition-transform hover:scale-105">
                  ¡Quiero ser socio!
              </Button>
          </div>
      </section>

      <Footer />
    </div>
  );
};

export default Index;
