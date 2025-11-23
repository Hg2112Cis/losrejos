import { Button } from "@/components/ui/button";
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from "@/components/ui/card";
import { Calendar, Mountain, Users, Zap, Compass } from "lucide-react"; // Añadido Zap y Compass para los Features
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";
import heroImage from "@/assets/hero-mountains.jpg";
import hikingImage from "@/assets/hiking-group.jpg";
import climbingImage from "@/assets/climbing.jpg";
import snowshoeImage from "@/assets/snowshoe.jpg";

// --- Datos de Actividades (Mejorados con una breve descripción) ---
const upcomingActivities = [
  {
    date: "01/02/2026",
    title: "Ruta de Raquetas: Pico Cueto",
    level: "Media-Alta",
    description: "Una travesía invernal desafiante por las cumbres nevadas de la Montaña Palentina. ¡Imprescindible equipo de seguridad!",
    image: snowshoeImage,
  },
  {
    date: "15/02/2026",
    title: "Curso Básico de Orientación",
    level: "Baja",
    description: "Aprende a usar mapa y brújula, y a navegar con GPS. Perfecto para novatos que quieren ganar autonomía.",
    image: hikingImage,
  },
  {
    date: "07/03/2026",
    title: "Travesía Circular Picos de Europa",
    level: "Alta",
    description: "Recorrido técnico de varios días por el macizo central. Solo para federados con experiencia en alta montaña.",
    image: climbingImage,
  },
];

// --- Componente de la Actividad (Extraído para mejorar la legibilidad) ---
const ActivityCard = ({ activity }) => {
  // Función para determinar el color del nivel (Mejora visual y UX)
  const getLevelColor = (level) => {
    switch (level) {
      case "Baja":
        return "bg-green-600 hover:bg-green-700";
      case "Media-Alta":
        return "bg-yellow-600 hover:bg-yellow-700";
      case "Alta":
        return "bg-red-600 hover:bg-red-700";
      default:
        return "bg-primary";
    }
  };

  return (
    <Card className="overflow-hidden group hover:shadow-xl transition-shadow duration-300">
      <div className="relative h-48 overflow-hidden">
        <img
          src={activity.image}
          alt={`Imagen de la actividad: ${activity.title}`} // Alt text mejorado (SEO/Accesibilidad)
          className="w-full h-full object-cover transition-transform group-hover:scale-105 duration-500" // Efecto hover más sutil
          loading="lazy" // Mejora de rendimiento
        />
        <div className={`absolute top-4 right-4 text-primary-foreground px-3 py-1 rounded-full text-sm font-bold shadow-md ${getLevelColor(activity.level)}`}>
          {activity.level}
        </div>
      </div>
      <CardHeader className="pb-3">
        <CardTitle className="text-xl font-semibold hover:text-primary transition-colors">{activity.title}</CardTitle>
        <CardDescription className="flex items-center gap-2 text-sm">
          <Calendar className="h-4 w-4 text-muted-foreground" />
          <time dateTime={activity.date.split('/').reverse().join('-')}>{activity.date}</time> {/* Formato de fecha para SEO */}
        </CardDescription>
      </CardHeader>
      <CardContent className="pt-0">
        <p className="text-sm text-gray-600 mb-4 line-clamp-2">{activity.description}</p> {/* Añadida descripción */}
        <Button className="w-full font-semibold" asChild>
          <a href={`/actividad/${activity.title.toLowerCase().replace(/\s/g, '-')}`}>
            Ver Detalles
          </a>
        </Button>
      </CardContent>
    </Card>
  );
};

const Index = () => {
  // Ajuste la ciudad para la sección About
  const city = "Cistierna"; 
  
  return (
    <div className="min-h-screen flex flex-col">
      {/* Añadido un metatag simple para SEO */}
      <title>Club de Montaña Los Rejos | Aventuras en la Montaña Oriental Leonesa</title>
      <Navbar />

      {/* 🚀 Hero Section - Ligeros ajustes de diseño y enfoque */}
      <section className="relative h-[650px] flex items-center justify-center overflow-hidden">
        <div
          className="absolute inset-0 bg-cover bg-center"
          style={{ backgroundImage: `url(${heroImage})` }}
        >
          <div className="absolute inset-0 bg-black/50 backdrop-blur-sm" /> {/* Oscurecimiento más claro y con ligero blur */}
        </div>
        <div className="relative z-10 text-center px-4 max-w-5xl">
          <h1 className="text-5xl md:text-7xl font-extrabold text-white mb-6 tracking-tight drop-shadow-lg">
            Club de Montaña Los Rejos
          </h1>
          <p className="text-xl md:text-3xl text-gray-100 font-medium mb-10 drop-shadow-md">
            Tu aventura comienza en **{city}**. Explorando la Montaña Oriental Leonesa desde 1995.
          </p>
          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <Button size="lg" className="text-lg font-bold py-7 px-8 transition-transform hover:scale-[1.03]">
              Únete al Club
            </Button>
            <Button size="lg" variant="outline" className="text-lg font-bold py-7 px-8 text-white border-white bg-transparent hover:bg-white/20 transition-transform hover:scale-[1.03]"> {/* Variante outline para contraste */}
              Ver Próximas Actividades
            </Button>
          </div>
        </div>
      </section>

      {/* 💡 About Section - Añadido un Feature más para completar la fila de 4 */}
      <section className="py-20 px-4 bg-gray-50"> {/* Color más neutro */}
        <div className="max-w-7xl mx-auto">
          <div className="text-center max-w-3xl mx-auto">
            <h2 className="text-4xl font-extrabold mb-4 text-gray-800">Quiénes Somos</h2>
            <p className="text-xl text-gray-600 leading-relaxed mb-12">
              Somos el corazón montañero de {city}.
            </p>
          </div>

          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-6">
            <Card className="text-center p-6 hover:shadow-lg transition-shadow">
              <Mountain className="h-10 w-10 text-primary mb-3 mx-auto" />
              <CardTitle className="text-lg">Actividades Variadas</CardTitle>
              <CardDescription className="text-sm">
                Senderismo, escalada, esquí de travesía y mucho más para todos los niveles.
              </CardDescription>
            </Card>

            <Card className="text-center p-6 hover:shadow-lg transition-shadow">
              <Users className="h-10 w-10 text-primary mb-3 mx-auto" />
              <CardTitle className="text-lg">Comunidad Activa</CardTitle>
              <CardDescription className="text-sm">
                Más de 200 socios que comparten la pasión por la montaña y el compañerismo.
              </CardDescription>
            </Card>

            <Card className="text-center p-6 hover:shadow-lg transition-shadow">
              <Calendar className="h-10 w-10 text-primary mb-3 mx-auto" />
              <CardTitle className="text-lg">Eventos Regulares</CardTitle>
              <CardDescription className="text-sm">
                Agenda de salidas programadas cada semana durante todo el año natural.
              </CardDescription>
            </Card>
            
            <Card className="text-center p-6 hover:shadow-lg transition-shadow">
              <Compass className="h-10 w-10 text-primary mb-3 mx-auto" /> {/* Nuevo feature */}
              <CardTitle className="text-lg">Formación y Seguridad</CardTitle>
              <CardDescription className="text-sm">
                Cursos de orientación, seguridad invernal y primeros auxilios en la montaña.
              </CardDescription>
            </Card>
          </div>
          
          <div className="text-center mt-10">
            <Button variant="link" className="text-lg font-semibold">
              Conoce nuestra Historia Completa →
            </Button>
          </div>
        </div>
      </section>

      {/* 🏔️ Featured Activities - Uso del nuevo componente y mejores prácticas */}
      <section className="py-20 px-4 bg-white">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-extrabold mb-4 text-center text-gray-800">
            Próximas Actividades Destacadas
          </h2>
          <p className="text-lg text-center text-gray-600 mb-12">
            ¡No te quedes sin plaza! Inscríbete a nuestras aventuras de la temporada.
          </p>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {upcomingActivities.map((activity, index) => (
              <ActivityCard key={index} activity={activity} /> // Uso del componente extraído
            ))}
          </div>

          <div className="text-center mt-12">
             <Button size="lg" variant="secondary" className="text-lg font-bold">
                Ver Calendario Completo
                <Zap className="ml-2 h-5 w-5" />
             </Button>
          </div>
        </div>
      </section>

      {/* 📞 CTA Section - Nueva sección para captar la atención final */}
      <section className="bg-primary py-16 px-4">
          <div className="max-w-5xl mx-auto text-center">
              <h2 className="text-3xl md:text-5xl font-extrabold text-primary-foreground mb-4">
                  ¿Listo para tu próxima cumbre?
              </h2>
              <p className="text-xl text-primary-foreground/90 mb-8">
                  Forma parte de la comunidad montañera de {city}. ¡Te esperamos!
              </p>
              <div className="flex flex-col sm:flex-row gap-4 justify-center">
                  <Button size="lg" variant="outline" className="text-lg font-bold py-7 px-8 text-primary border-white bg-white hover:bg-gray-100 transition-transform hover:scale-[1.03]">
                      ¡Quiero Unirme!
                  </Button>
              </div>
          </div>
      </section>

      <Footer />
    </div>
  );
};

export default Index;
